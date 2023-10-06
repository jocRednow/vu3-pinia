<template>
  <div class="about">
    <h1>About page</h1>
  </div>
</template>

<script setup lang="ts">
  async function postJSON() {
  try {
    const response = await fetch("https://api.kinopoisk.dev/v1/studio", {
      method: "GET",
      headers: {
        "X-API-KEY": "4Q2T31C-T4D4AM3-ME8QHQ0-F9W4CNT",
      },
    });

    const result = await response.json();
    console.log("Success:", result);
    return result;
  } catch (error) {
    console.error("Error:", error);
  }
}

const data = postJSON();

</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
