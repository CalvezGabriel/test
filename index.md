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

<div id="fiba-news">Chargement de la dernière actualité...</div>
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
    document.getElementById("fiba-news").innerHTML =
      `<a href="${lien}" target="_blank">${titre}</a>`;
  } catch (e) {
    document.getElementById("fiba-news").innerText =
      "Impossible de charger la dernière actualité 😞";
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
