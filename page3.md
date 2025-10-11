## <span style="color:#00bfff;">📊 Scores NBA en direct</span>

<div id="live-scores" style="background-color:#333; color:white; padding:1em; border-radius:10px; max-width:700px; margin-top:1em;">
  Chargement des scores...
</div>

<script>
async function fetchLiveScores() {
  try {
    const response = await fetch('https://www.balldontlie.io/api/v1/games?start_date=2025-10-11&end_date=2025-10-11');
    const data = await response.json();
    const games = data.data;
    if (games.length === 0) {
      document.getElementById('live-scores').innerHTML = 'Aucun match NBA en cours aujourd\'hui.';
      return;
    }
    let html = '<ul style="list-style:none; padding-left:0;">';
    games.forEach(game => {
      const homeTeam = game.home_team.full_name;
      const awayTeam = game.visitor_team.full_name;
      const homeScore = game.home_team_score;
      const awayScore = game.visitor_team_score;
      const status = game.status;
      const date = new Date(game.date);
      html += `<li style="margin-bottom:1em;">
        <strong>${homeTeam} vs ${awayTeam}</strong><br>
        ${date.toLocaleString('fr-FR')} - ${status}<br>
        Score: ${homeScore} - ${awayScore}
      </li>`;
    });
    html += '</ul>';
    document.getElementById('live-scores').innerHTML = html;
  } catch (error) {
    document.getElementById('live-scores').innerHTML = '<p style="color:red;">Erreur de chargement des scores.</p>';
    console.error(error);
  }
}
fetchLiveScores();
</script>
