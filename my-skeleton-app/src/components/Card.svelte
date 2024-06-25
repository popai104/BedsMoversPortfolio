<script>
  export let title;
  export let description;
  export let imageUrl;
</script>

<div class="card">
  <img src={imageUrl} alt={title} class="card-image" />
  <div class="card-content">
    <h2>{title}</h2>
    <p>{description}</p>
  </div>
</div>

<style>
  .card {
    border: 1px solid #ccc;
    border-radius: 8px;
    overflow: hidden;
    width: 300px;
    margin: 16px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  }
  .card-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
  }
  .card-content {
    padding: 16px;
  }
  .card-content h2 {
    margin: 0 0 8px;
  }
</style>
