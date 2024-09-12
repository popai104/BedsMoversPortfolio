<script>
  import Card from '../components/Card.svelte';

  // Qui si aggiungono i fottuti progetti 
  let projects = [
    { title: 'Matteo gay', description: 'Descrizione del progetto 1', imageUrl: 'https://via.placeholder.com/300' },
    { title: 'Suca', description: 'Descrizione del progetto 2', imageUrl: 'https://via.placeholder.com/300' },
    { title: 'Matteo gay', description: 'Descrizione del progetto 1', imageUrl: 'https://via.placeholder.com/300' },
    { title: 'Suca', description: 'Descrizione del progetto 2', imageUrl: 'https://via.placeholder.com/300' },
    { title: 'Matteo gay', description: 'Descrizione del progetto 1', imageUrl: 'https://via.placeholder.com/300' },
    { title: 'Suca', description: 'Descrizione del progetto 2', imageUrl: 'https://via.placeholder.com/300' },
    { title: 'Matteo gay', description: 'Descrizione del progetto 1', imageUrl: 'https://via.placeholder.com/300' },
    { title: 'Suca', description: 'Descrizione del progetto 2', imageUrl: 'https://via.placeholder.com/300' },

  ];
</script>

<div class="project-cards justify-center">
  {#each projects as project}
    <Card title={project.title} description={project.description} imageUrl={project.imageUrl} />
  {/each}
</div>

<style>
  .project-cards {
    display: flex;
    flex-wrap: wrap;
  }
</style>
