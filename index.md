# BASKETBL🏀G

# Bienvenue sur mon site web dédié au basketball!  

---

## L'actu Internationale

1. [Site BasketEurope :](https://www.basketeurope.com)
2. [Site BeBasket :](https://www.bebasket.fr)
3. [Site de la FIBA :](https://www.fiba.basketball/fr)

---

## Les plus belles actions NBA de la saison 2024-25 
<iframe width="560" height="315"
  src="https://www.youtube.com/embed/j2kvgwLapKk"
  title="YouTube video player"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>

---

## Les dernières news

<div id="fiba-news" style="
  border: 2px solid #004aad;
  border-radius: 12px;
  padding: 1.5em;
  margin-top: 1em;
  background: #f5f8ff;
  font-family: system-ui, sans-serif;
  max-width: 700px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.05);
">
  <p>Chargement de la dernière actualité...</p>
</div>

<script>
async function chargerDerniereActuFIBA() {
  try {
    const response = await fetch("https://www.fiba.basketball/news/rss");
    const text = await response.text();
    const parser = new DOMParser();
    const xml = parser.parseFromString(text, "application/xml");
    const item = xml.querySelector("item");
    const titre = item.querySelector("title").textContent;
    const lien = item.querySelector("link").textContent;
    const description = item.querySelector("description").textContent;
    const date = new Date(item.querySelector("pubDate").textContent);

    document.getElementById("fiba-news").innerHTML = `
      <h2 style="color:#004aad; margin-top:0;">${titre}</h2>
      <p style="color:#333; font-size: 1em; line-height:1.4;">
        ${description.substring(0, 200)}...
      </p>
      <p style="font-size: 0.9em; color:#666;">🗓️ ${date.toLocaleDateString("fr-FR")}</p>
      <a href="${lien}" target="_blank" style="
        display: inline-block;
        background: #004aad;
        color: white;
        text-decoration: none;
        padding: 0.6em 1em;
        border-radius: 8px;
        font-weight: bold;
        transition: background 0.2s ease;
      " onmouseover="this.style.background='#002e6b'"
        onmouseout="this.style.background='#004aad'">
        🔗 Lire l’article complet sur FIBA.basketball
      </a>
    `;
  } catch (e) {
    document.getElementById("fiba-news").innerHTML =
      "<p style='color:red;'>⚠️ Impossible de charger la dernière actualité pour le moment.</p>";
  }
}

chargerDerniereActuFIBA();
</script>

---

## 💬 Me contacter

Tu peux me retrouver ici :

- [GitHub](https://github.com/monprofil)
- [LinkedIn](https://linkedin.com/in/monprofil)
- [Email](mailto:contact@monsite.com)

---

> ✨ *“La simplicité est la sophistication suprême.”* — Léonard de Vinci

- [Page 1](page1.md)
- [Page 2](page2.md)
- [Page 3](page3.md)
