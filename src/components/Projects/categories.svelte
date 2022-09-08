<script>
  export let categories;
  export let onCategoryClick;
</script>

<div>
  <h3 class="tac">Kategoriler</h3>
  <button class="btn w-full">Etikete Göre Filtrele</button>
  <div class="w-full tac">
    {#each categories as c (c)}
      <div class="category" on:click={onCategoryClick}>{c}</div>
    {/each}
  </div>
</div>

<style lang="scss">
  .category {
    background-color: #fff;
    border-bottom: 1px solid #bbb;
    cursor: pointer;
    padding: 0.5rem 1rem;
    transition: all 0.4s ease;
    &:hover {
      background-color: #eee;
    }
  }
</style>
