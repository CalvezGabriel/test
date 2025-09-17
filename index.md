# TEST
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Site test</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <nav>
    <a href="#" onclick="loadPage('page1.md')">Page 1</a>
    <a href="#" onclick="loadPage('page2.md')">Page 2</a>
    <a href="#" onclick="loadPage('page3.md')">Page 3</a>
  </nav>

  <main id="content">Chargement...</main>

  <!-- Librairie Markdown -->
  <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
  <script src="script.js"></script>
</body>
</html>
