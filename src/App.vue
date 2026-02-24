<script>
import {last, pr} from './weights.js'

export default {
  data() {
    return {
      last,
      pr,
    }
  }
}
</script>

<template>
  <img src="./assets/lasha.png">
  <table>
    <thead>
      <tr>
        <th>Exercise</th>
        <th>Last Week</th>
        <th>PR</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Snatch</td>
        <td>{{ last.s }}</td>
        <td>{{ pr.s }}</td>
      </tr>
      <tr>
        <td>Clean & Jerk</td>
        <td>{{ last.cj }}</td>
        <td>{{ pr.cj }}</td>
      </tr>
      <tr>
        <td>Back Squat</td>
        <td>{{ last.bs }}</td>
        <td>{{ pr.bs }}</td>
      </tr>
      <tr>
        <td>Clean Pull</td>
        <td>{{ last.cp }}</td>
        <td>{{ pr.cp }}</td>
      </tr>
      <tr>
        <td>Front Squat</td>
        <td>{{ last.fs }}</td>
        <td>{{ pr.fs }}</td>
      </tr>
      <tr>
        <td>Snatch Pull</td>
        <td>{{ last.sp }}</td>
        <td>{{ pr.sp }}</td>
      </tr>
    </tbody>
  </table> 
</template>

<style>
:root {
  --bg: #0b0f14;
  --card: #141a22;
  --accent: #ff3b30;
  --text: #f5f7fa;
  --muted: #8b98a7;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: var(--bg);
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  color: var(--text);
  display: flex;
  justify-content: center;
}

img {
  display: block;
  margin: 1.5rem auto 1.25rem;
  width: 80%;
  max-width: 240px;
  height: auto;
}

table {
  width: 100%;
  max-width: 420px;
  border-collapse: collapse;
  background: var(--card);
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
  font-size: 0.95rem;
}

thead {
  background: rgba(255, 59, 48, 0.08);
}

th {
  padding: 0.9rem 0.5rem;
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--muted);
}

td {
  padding: 0.95rem 0.5rem;
  font-weight: 600;
  font-size: 1rem;
}

th:first-child,
td:first-child {
  text-align: left;
  padding-left: 1.1rem;
}

th:not(:first-child),
td:not(:first-child) {
  text-align: center;
}

tbody tr {
  transition: background 0.15s ease;
}

tbody tr:not(:last-child) {
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

tbody tr:hover {
  background: rgba(255, 59, 48, 0.06);
}

tbody td:last-child {
  color: var(--accent);
}

@media (max-width: 390px) {
  table {
    font-size: 0.9rem;
  }

  td {
    padding: 0.85rem 0.4rem;
  }
}
</style>