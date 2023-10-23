<script setup lang="ts">
import BoardInterface from './components/BoardInterface.vue';
import PlayerInterface from './components/PlayerInterface.vue';
import LibraryInterface from './components/LibraryInterface.vue'
import SearchInterface from './components/SearchInterface.vue'
</script>

<template>
  <div class="mainBoard">
    <nav>
      <SearchInterface class="card" />
      <LibraryInterface class="card library" />
    </nav>
    <main>
      <BoardInterface class="card" />
    </main>
    <footer>
      <PlayerInterface />
    </footer>
  </div>

</template>

<style lang="scss">

.mainBoard {
  display: grid;
  height: 100%;
  gap: 15px;
  grid-template-areas:
  "nav main main"
  "player player player";
  grid-template-columns: 20em 1fr;
  grid-template-rows: 90% 1fr;
  .card{
      background: var(--mainSection);
      padding: var(--cardPadding);
      border-radius: var(--mainBorder);
    }
  .library {
    height: 100% !important;
  }
}

main {
  grid-area: main;
  background: var(--mainSection);
  border-radius: var(--mainBorder);
}

nav {
  display: flex;
  grid-area: nav;
  flex-direction: column;
  gap:10px;
}

footer {
  grid-area: player;
}

</style>
