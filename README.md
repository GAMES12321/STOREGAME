<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Top Jeux à Télécharger - Canada</title>
<style>
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(to right, #fceabb, #f8b500);
    padding: 20px;
  }
  h1 {
    text-align: center;
    color: #2c3e50;
  }
  .top-controls {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 20px;
    gap: 10px;
    position: relative;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
  }
  #search {
    padding: 12px 20px;
    font-size: 20px;
    border-radius: 12px;
    border: 2px solid #e67e22;
    outline: none;
    width: 100%;
    box-sizing: border-box;
    box-shadow: 0 0 10px rgba(230, 126, 34, 0.6);
    transition: box-shadow 0.3s ease;
    z-index: 10;
    position: relative;
  }
  #search:focus {
    box-shadow: 0 0 15px 3px #e67e22;
  }
  #suggestions {
    position: absolute;
    top: 60px;
    left: 0;
    right: 0;
    background: white;
    border-radius: 0 0 12px 12px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    max-height: 200px;
    overflow-y: auto;
    z-index: 20;
    display: none;
  }
  #suggestions div {
    padding: 10px 20px;
    cursor: pointer;
    border-bottom: 1px solid #eee;
    font-weight: bold;
    color: #2c3e50;
  }
  #suggestions div:hover {
    background-color: #e67e22;
    color: white;
  }
  .language-switcher select {
    padding: 8px 15px;
    font-size: 16px;
    border-radius: 8px;
    border: none;
    height: 48px;
  }
  .categories {
    text-align: center;
    margin-bottom: 20px;
  }
  .categories button {
    background: white;
    border: 2px solid #e67e22;
    color: #e67e22;
    padding: 8px 15px;
    margin: 5px;
    border-radius: 20px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.3s;
  }
  .categories button.active,
  .categories button:hover {
    background: #e67e22;
    color: white;
  }
  .container {
    max-width: 1200px;
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
  }
  .game-card {
    background: white;
    border-radius: 15px;
    width: 260px;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 15px;
    text-align: center;

    /* إطار مضلل */
    border: 2px solid #27ae60;
    box-shadow: 0 4px 15px rgba(39, 174, 96, 0.6);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  .game-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 8px 30px rgba(39, 174, 96, 0.9);
  }
  .game-card img {
    width: 100%;
    height: 160px;
    object-fit: cover;
    border-radius: 10px;
  }
  .game-title {
    font-size: 18px;
    font-weight: bold;
    margin: 10px 0 5px;
    color: #2c3e50;
  }
  .stars {
    color: #f1c40f;
    margin-bottom: 10px;
  }
  .download-btn {
    margin-top: auto;
    padding: 10px 20px;
    background-color: #27ae60;
    color: white;
    border: none;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(39, 174, 96, 0.7);
    text-decoration: none;
    font-weight: bold;
    transition: background-color 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
  }
  .download-btn:hover {
    background-color: #1e8449;
    box-shadow: 0 6px 18px rgba(30, 132, 73, 0.9);
  }
  .download-count {
    margin-top: 8px;
    font-size: 14px;
    color: #555;
  }
</style>
</head>
<body>

<h1 id="page-title">Top Jeux à Télécharger - Canada 🇨🇦</h1>

<div class="top-controls">
  <input type="text" id="search" placeholder="🔍 Rechercher par nom ou numéro..." autocomplete="off"/>
  <div id="suggestions"></div>
  <div class="language-switcher">
    <select id="language" onchange="changeLanguage()">
      <option value="fr">Français</option>
      <option value="en">English</option>
      <option value="nl">Nederlands</option>
      <option value="de">Deutsch</option>
      <option value="ar">العربية</option>
    </select>
  </div>
</div>

<div class="categories" id="categories">
  <button onclick="filterByCategory('all')" class="active">🌐 Tous</button>
  <button onclick="filterByCategory('action')">🎯 Action</button>
  <button onclick="filterByCategory('adventure')">🗺️ Aventure</button>
  <button onclick="filterByCategory('sports')">⚽ Sport</button>
  <button onclick="filterByCategory('logic')">🧠 Logique</button>
</div>

<div class="container" id="games-container">
  <!-- jeux dynamiques -->
</div>

<script>
  const games = [
    { name: "Block Blast!", category: "logic" },
    { name: "Roblox", category: "adventure" },
    { name: "Subway Surfers", category: "adventure" },
    { name: "Ludo King", category: "logic" },
    { name: "Pizza Ready!", category: "logic" },
    { name: "No WiFi - Antistress Relax Toys", category: "logic" },
    { name: "Free Fire", category: "action" },
    { name: "Cookingdom", category: "logic" },
    { name: "My Talking Tom 2", category: "adventure" },
    { name: "Free Fire MAX", category: "action" },
    { name: "Snake Clash!", category: "action" },
    { name: "Hole.io", category: "logic" },
    { name: "8 Ball Pool", category: "sports" },
    { name: "Brainy Prankster", category: "logic" },
    { name: "Candy Crush Saga", category: "logic" },
    { name: "Gossip Harbor: Merge & Story", category: "logic" },
    { name: "Gardenscapes", category: "logic" },
    { name: "Royal Match", category: "logic" },
    { name: "Coin Master", category: "logic" },
    { name: "Pokémon TCG Pocket", category: "logic" }
  ];

  const downloadLinks = [
    "https://example.com/blockblast",
    "https://example.com/roblox",
    "https://example.com/subwaysurfers",
    "https://example.com/ludoking",
    "https://example.com/pizzaready",
    "https://example.com/nowifi",
    "https://example.com/freefire",
    "https://example.com/cookingdom",
    "https://example.com/mytalkingtom2",
    "https://example.com/freefiremax",
    "https://example.com/snakeclash",
    "https://example.com/holeio",
    "https://example.com/8ballpool",
    "https://example.com/brainyprankster",
    "https://example.com/candycrush",
    "https://example.com/gossipharbor",
    "https://example.com/gardenscapes",
    "https://example.com/royalmatch",
    "https://example.com/coinmaster",
    "https://example.com/pokemontcg"
  ];

  const translations = {
    fr: { title: "Top Jeux à Télécharger - Canada 🇨🇦", download: "Télécharger", search: "Rechercher par nom ou numéro..." },
    en: { title: "Top Games to Download - Canada 🇨🇦", download: "Download", search: "Search by name or number..." },
    nl: { title: "Top Spellen om te Downloaden - Canada 🇨🇦", download: "Downloaden", search: "Zoek op naam of nummer..." },
    de: { title: "Top-Spiele zum Herunterladen - Kanada 🇨🇦", download: "Herunterladen", search: "Suche nach Name oder Nummer..." },
    ar: { title: "أفضل الألعاب للتحميل - كندا 🇨🇦", download: "تحميل", search: "ابحث باسم اللعبة أو رقمها..." }
  };

  const downloadCounts = {};
  const increments = [4, 10, 15, 13];

  function generateStars() {
    const rating = Math.floor(Math.random() * 2) + 4;
    return "⭐".repeat(rating);
  }

  function renderGames(lang = "fr", category = "all", search = "") {
    const container = document.getElementById("games-container");
    container.innerHTML = "";

    let filteredGames = games.map((game, index) => ({ ...game, index: index + 1 }));

    if (category !== "all") {
      filteredGames = filteredGames.filter(game => game.category === category);
    }

    if (search.trim() !== "") {
      const term = search.toLowerCase();
      filteredGames = filteredGames.filter(game =>
        game.name.toLowerCase().includes(term) || game.index.toString() === term
      );
    }

    // Sort by downloadCounts descending
    filteredGames.sort((a,b) => (downloadCounts[b.index] || 0) - (downloadCounts[a.index] || 0));

    filteredGames.forEach((game) => {
      if (!downloadCounts[game.index]) {
        downloadCounts[game.index] = Math.floor(Math.random() * 1000) + 100; 
      }
      const card = document.createElement("div");
      card.className = "game-card";
      card.innerHTML = `
        <img src="https://via.placeholder.com/260x160?text=${encodeURIComponent(game.name)}" alt="${game.name}" />
        <div class="game-title">${game.name}</div>
        <div class="stars">${generateStars()}</div>
        <a href="${downloadLinks[game.index - 1]}" target="_blank" class="download-btn">${translations[lang].download}</a>
        <div class="download-count" id="count-${game.index}">${downloadCounts[game.index]} ${lang === 'ar' ? 'تحميلات' : lang === 'en' ? 'downloads' : lang === 'nl' ? 'downloads' : lang === 'de' ? 'Downloads' : 'téléchargements'}</div>
      `;
      container.appendChild(card);
    });

    document.getElementById("page-title").textContent = translations[lang].title;
    document.getElementById("search").placeholder = translations[lang].search;
  }

  function incrementDownloadsRandomly() {
    for (const key in downloadCounts) {
      const inc = increments[Math.floor(Math.random() * increments.length)];
      downloadCounts[key] += inc;
      const el = document.getElementById("count-" + key);
      if (el) {
        const lang = document.getElementById("language").value;
        el.textContent = `${downloadCounts[key]} ${lang === 'ar' ? 'تحميلات' : lang === 'en' ? 'downloads' : lang === 'nl' ? 'downloads' : lang === 'de' ? 'Downloads' : 'téléchargements'}`;
      }
    }
  }

  function getMostDownloadedGames() {
    let rankedGames = games.map((game, i) => ({
      ...game,
      index: i+1,
      downloads: downloadCounts[i+1] || 0
    }));
    rankedGames.sort((a,b) => b.downloads - a.downloads);
    return rankedGames.slice(0, 5);
  }

  function showSuggestions() {
    const input = document.getElementById("search");
    const suggestions = document.getElementById("suggestions");
    const val = input.value.toLowerCase();

    if (val.length === 0) {
      suggestions.style.display = "none";
      return;
    }

    const mostDownloaded = getMostDownloadedGames();

    const filtered = mostDownloaded.filter(game => {
      const nameMatch = game.name.toLowerCase().includes(val);
      const numberMatch = game.index.toString().startsWith(val);
      return nameMatch || numberMatch;
    });

    if (filtered.length === 0) {
      suggestions.style.display = "none";
      return;
    }

    suggestions.innerHTML = filtered.map(game => `<div onclick="selectSuggestion(${game.index}, '${game.name}')">${game.name}</div>`).join("");
    suggestions.style.display = "block";
  }

  function selectSuggestion(index, name) {
    document.getElementById("search").value = name;
    document.getElementById("suggestions").style.display = "none";
    filterGames();
  }

  function changeLanguage() {
    const lang = document.getElementById("language").value;
    document.body.style.direction = (lang === "ar") ? "rtl" : "ltr";
    renderGames(lang, selectedCategory, document.getElementById("search").value);
  }

  let selectedCategory = "all";

  function filterByCategory(cat) {
    selectedCategory = cat;
    document.querySelectorAll(".categories button").forEach(btn => btn.classList.remove("active"));
    const index = ["all", "action", "adventure", "sports", "logic"].indexOf(cat);
    document.querySelectorAll(".categories button")[index].classList.add("active");

    const lang = document.getElementById("language").value;
    renderGames(lang, cat, document.getElementById("search").value);
  }

  function filterGames() {
    const searchVal = document.getElementById("search").value;
    const lang = document.getElementById("language").value;
    renderGames(lang, selectedCategory, searchVal);
    showSuggestions();
  }

  window.onload = () => {
    renderGames("fr");
    setInterval(() => {
      incrementDownloadsRandomly();
    }, 1500);

    const searchInput = document.getElementById("search");
    searchInput.addEventListener("input", showSuggestions);
    searchInput.addEventListener("focus", showSuggestions);
    searchInput.addEventListener("blur", () => {
      setTimeout(() => {
        document.getElementById("suggestions").style.display = "none";
      }, 200);
    });
  };
</script>

</body>
</html>
