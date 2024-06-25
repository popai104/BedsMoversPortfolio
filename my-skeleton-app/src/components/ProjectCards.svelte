<script>
  import Card from './Card.svelte';

  let projects = [
    { title: 'Progetto 1', description: 'Descrizione del progetto 1', imageUrl: 'https://via.placeholder.com/300' },
    { title: 'Progetto 2', description: 'Descrizione del progetto 2', imageUrl: 'https://via.placeholder.com/300' },
  ];

  function addProject() {
    projects = [...projects, { title: `Progetto ${projects.length + 1}`, description: `Descrizione del progetto ${projects.length + 1}`, imageUrl: 'https://via.placeholder.com/300' }];
  }
</script>

<div class="project-cards">
  {#each projects as project}
    <Card title={project.title} description={project.description} imageUrl={project.imageUrl} />
  {/each}
</div>
<button on:click={addProject}>Aggiungi Progetto</button>

<style>
  .project-cards {
    display: flex;
    flex-wrap: wrap;
  }
  button {
    margin: 16px;
    padding: 8px 16px;
    font-size: 16px;
    cursor: pointer;
  }
</style>
