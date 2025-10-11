# <span style="color:#004aad;">BASKETBL🏀G</span>

<p style="font-size:1.2em; text-align:center;">
Bienvenue sur mon site web dédié au <strong>basketball</strong>! 🏀
</p>

<hr style="border-top:2px solid #004aad;">

## <span style="color:#ff4500;">L'actu Internationale</span>

<ul>
  <li><a href="https://www.basketeurope.com" target="_blank" style="color:#004aad; text-decoration:none;">Site BasketEurope</a></li>
  <li><a href="https://www.bebasket.fr" target="_blank" style="color:#004aad; text-decoration:none;">Site BeBasket</a></li>
  <li><a href="https://www.fiba.basketball/fr" target="_blank" style="color:#004aad; text-decoration:none;">Site de la FIBA</a></li>
</ul>

<hr style="border-top:2px solid #004aad;">

## <span style="color:#ff4500;">Les plus belles actions NBA de la saison 2024-25</span>

<p style="text-align:center;">
<iframe width="560" height="315"
  src="https://www.youtube.com/embed/j2kvgwLapKk"
  title="YouTube video player"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>
</p>

<hr style="border-top:2px solid #004aad;">

## <span style="color:#ff4500;">Les dernières news</span>

<div id="fiba-news" style="
  background-color:#333; 
  color:#fff; 
  padding:1em; 
  border-radius:10px; 
  max-width:700px;
  margin-top:1em;
">
  Chargement en cours...
</div>

<script>
async function chargerDerniereActuFIBA() {
  try {
    // Utilisation du proxy pour contourner le CORS
    const response = await fetch("https://api.allorigins.win/raw?url=https://www.fiba.basketball/news/rss");
    const text = await response.text();
    const parser = new DOMParser();
    const xml = parser.parseFromString(text, "application/xml");

    // Sélection du premier article
    const item = xml.querySelector("item");
    const titre = item.querySelector("title").textContent;
    const lien = item.querySelector("link").textContent;
    const description = item.querySelector("description").textContent;
    const date = new Date(item.querySelector("pubDate").textContent);

    // Création du bloc HTML
    document.getElementById("fiba-news").innerHTML = `
      <h3 style="color:#ff9800; margin-top:0;">${titre}</h3>
      <p style="font-size:0.95em; color:#ddd;">${description.substring(0, 200)}...</p>
      <p style="font-size:0.8em; color:#bbb;">🗓️ ${date.toLocaleDateString("fr-FR")}</p>
      <a href="${lien}" target="_blank" style="
        display:inline-block;
        background-color:#004aad;
        color:white;
        padding:0.5em 1em;
        border-radius:6px;
        text-decoration:none;
        font-weight:bold;
      ">Lire l'article complet</a>
    `;
  } catch (e) {
    document.getElementById("fiba-news").innerHTML = "<p style='color:red;'>⚠️ Impossible de charger la dernière actualité.</p>";
  }
}

// Lancement de la fonction
chargerDerniereActuFIBA();
</script>
</p>

<hr style="border-top:2px solid #004aad;">

## <span style="color:#ff4500;">💬 Me contacter</span>

<p>Tu peux me retrouver ici :</p>

<ul>
  <li><a href="https://github.com/CalvezGabriel" target="_blank" style="color:#004aad;">GitHub</a></li>
</ul>

<hr style="border-top:2px solid #004aad;">

<p style="text-align:center;">
Pages supplémentaires : 
<a href="page1.md" style="color:#004aad;">Article 1</a> | 
<a href="page2.md" style="color:#004aad;">Article 2</a> | 
<a href="page3.md" style="color:#004aad;">Article 3</a>
</p>

<body style="background-color:#1c1c1c; color:#f5f5f5; font-family: Arial, sans-serif; padding:2em;"> 

