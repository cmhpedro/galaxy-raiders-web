<template>
  <div id="canvas">
    <div id="deep-space" />
    <div id="menu">
      <h1 class="title">Placar</h1>
      <table>
        <tr>
          <th>Data e Hora</th>
          <th>Pontuação</th>
          <th>Asteroides destruídos</th>
        </tr>
        <tr v-for="(data, timestamp) in games" :key="timestamp">
          <td>{{ timestamp }}</td>
          <td>{{ data['score'] }}</td>
          <td>{{data['asteroids destroyed']}}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import leaderboard from '~/score/Leaderboard.json';

export default {
  data() {
    return {
      games: leaderboard
    };
  }
};
</script>

<style>
tr {
  font-size: 1.5rem;
  text-align: center;
}

th {
  padding: 1rem;

  background-color: #36bbf5;
  color: #fff;
  border: 1px solid #36bbf5;
  border-radius: 5px;
}

td {
  padding: 1rem;

  background-color: #fff;
  color: #36bbf5;
  border: 1px solid #36bbf5;
  border-radius: 5px;
}
</style>
