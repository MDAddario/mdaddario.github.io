<script>
import {snatch, clean_jerk, cycle} from './weights.js'
export default {
  data() {
    return { snatch, clean_jerk, cycle }
  }
}
</script>

<template>
  <div class="row">
    <table class="mini">
      <thead><tr><th>Snatch</th></tr></thead>
      <tbody><tr><td>{{ snatch }}</td></tr></tbody>
    </table>
    <img src="./assets/lasha.png">
    <table class="mini">
      <thead><tr><th>Clean Jerk</th></tr></thead>
      <tbody><tr><td>{{ clean_jerk }}</td></tr></tbody>
    </table>
  </div>
  <table class="max">
    <thead>
      <tr>
        <th>Week</th>
        <th>Back<br>Squat</th>
        <th>Clean<br>Pull</th>
        <th>Front<br>Squat</th>
        <th>Snatch<br>Pull</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="week in cycle" :key="week.week">
        <td>{{ week.week }}</td>
        <td>{{ week.back_squat }}</td>
        <td>{{ week.clean_pull }}</td>
        <td>{{ week.front_squat }}</td>
        <td>{{ week.snatch_pull }}</td>
      </tr>
    </tbody>
  </table> 
</template>

<style>
/* page */
:host, body {
  background: #0f0f10;
  color: #e5e5e5;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  margin: 0;
  padding: 16px;
}

/* row with snatch / image / cj */
.row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 8px;
  margin-bottom: 20px;
}

/* athlete image */
img {
  width: 160px;
  height: auto;
  object-fit: contain;
}

/* tables */
table {
  border-collapse: collapse;
  text-align: center;
}

/* mini tables (snatch / cj) */
table.mini {
  width: 90px;
  background: #18181b;
  border-radius: 10px;
  overflow: hidden;
}

table.mini th {
  font-size: 14px;
  font-weight: 600;
  padding: 6px;
  background: #222226;
}

table.mini td {
  font-size: 28px;
  font-weight: 700;
  padding: 10px 0;
}

/* max table */
table.max {
  width: 100%;
  background: #18181b;
  border-radius: 12px;
  overflow: hidden;
}

/* headers */
table.max th {
  font-size: 12px;
  font-weight: 600;
  padding: 8px 4px;
  background: #222226;
}

/* cells */
table.max td {
  font-size: 15px;
  padding: 10px 4px;
  border-top: 1px solid #2a2a2e;
}

/* first column */
table.max td:first-child {
  font-weight: 600;
  color: #bdbdbd;
}

/* PR row highlight */
table.max tbody tr:last-child {
  background: #202024;
  font-weight: 700;
}
</style>