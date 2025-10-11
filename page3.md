# Score en directs
<div id="live-scores" style="font-family: Arial, sans-serif; font-size: 1.2em; background-color: #1a1a1a; color: white; padding: 1em; border-radius: 8px;">
  Chargement des scores...
</div>

<script>
  async function fetchLiveScores() {
    try {
      const response = await fetch('https://www.balldontlie.io/api/v1/games?team_ids[]=&start_date=2025-10-12&end_date=2025-10-12');
      const data = await response.json();
      const games = data.data;

      if (games.length === 0) {
        document.getElementById('live-scores').innerHTML = 'Aucun match NBA en cours aujourd\'hui.';
        return;
      }

      let html = '<ul>';
      games.forEach(game => {
        const homeTeam = game.home_team.full_name;
        const awayTeam = game.visitor_team.full_name;
        const homeScore = game.home_team_score;
        const awayScore = game.visitor_team_score;
        const status = game.status;
        const date = new Date(game.date);
        const formattedDate = date.toLocaleString('fr-FR');

        html += `
          <li>
            <strong>${homeTeam} vs ${awayTeam}</strong><br>
            ${formattedDate} - ${status}<br>
            Score: ${homeScore} - ${awayScore}
          </li>
        `;
      });
      html += '</ul>';
      document.getElementById('live-scores').innerHTML = html;
    } catch (error) {
      document.getElementById('live-scores').innerHTML = 'Erreur de chargement des scores.';
      console.error(error);
    }
  }

  fetchLiveScores();
</script>
