<script>
  import projectsData from "../../projectsData.json";
  import Categories from "./categories.svelte";
  import List from "./list.svelte";
  const categorySet = new Set();
  projectsData.forEach((p) => {
    p.tags.forEach((t) => {
      categorySet.add(t);
    });
  });
  const categories = Array.from(categorySet);
  let filteredProjects = projectsData;
  function categoryClicked(e) {
    const selectedCategory = e.target.innerText;
    filteredProjects = selectedCategory
      ? projectsData.filter((p) => p.tags.includes(selectedCategory))
      : projectsData;
  }
</script>

<div class="projects">
  <div class="categories">
    <Categories {categories} onCategoryClick={categoryClicked} />
  </div>
  <div class="list">
    <List projects={filteredProjects} />
  </div>
</div>

<style lang="scss">
  .projects {
    display: flex;
    gap: 1rem;
  }

  .categories {
    width: 20%;
  }

  .list {
    width: 80%;
  }
</style>
