<script>
  export let projects;
</script>

<div>
  <h3 class="tac">Projeler</h3>
  <div class="cards">
    {#each projects as p (p.slug)}
      <div class="card">
        <a href={`/proje/${p.slug}`}>
          <div class="img">
            <img src={p.img} alt="tweeter" />
          </div>
          <div class="title">{p.title}</div>
          <div class="tags">
            {#each p.tags as tag}
              <div class="tag">{tag}</div>
            {/each}
          </div>
        </a>
      </div>
    {/each}
  </div>
</div>

<style lang="scss">
  .cards {
    display: flex;
    flex-wrap: wrap;
  }

  .card {
    margin: 0.8rem;
    margin-top: 0;
    width: 250px;
    padding: 1rem;
    border-radius: 10px;
    transition: all 0.3s ease-in;
    box-shadow: 4px 4px 4px 0px rgba(100, 100, 100, 0.5);
    &:hover {
      transform: rotate(-2deg);
      box-shadow: 10px 10px 4px 0px rgba(100, 100, 100, 0.5);
    }
    & a > * {
      margin-bottom: 0.5rem;
    }
  }

  .img {
    width: auto;
    height: auto;
    border-radius: 5px;
    overflow: hidden;
  }

  .title {
    font-size: 1.2rem;
  }

  .tags {
    display: flex;
    gap: 1rem;
    margin-block-start: 0.5rem;
    margin-block-end: 0.5rem;
    flex-wrap: wrap;
  }

  .tag {
    background-color: #ddd;
    padding: 0.2rem 0.5rem;
  }
</style>
