<script>
  export let title;
  export let description;
  export let imageUrl;
</script>

<div class="grid-container justify-center align-center">
  <div class="card">
    <div class="card-image-container">
      <img src={imageUrl} alt={title} class="card-image" />
      <div class="overlay">
        <h2 class="overlay-title">{title}</h2>
      </div>
    </div>
    <div class="card-content">
      <p>{description}</p>
    </div>
  </div>
</div>

<style>

  .grid-container {
  align-content: center;
  align-items: center;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 10px;
  padding: 8px;
}

  .card {
    align-content: center;
    align-items: center;
    background-color: #340f1b;
    border: 1px solid #ccc;
    border-radius: 12px;
    overflow: hidden;
    width: 300px;
    margin: 16px;
    box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.1);

  }
  .card-image-container {
    position: relative;
  }
  .card-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
  }
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    color: white;
    text-align: center;
    padding: 10px;
    opacity: 0;
    transition: opacity 0.3s ease;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .card-image-container:hover .overlay {
    opacity: 1;
  }
  .overlay-title {
    margin: 0;
  }
  .card-content {
    padding: 16px;
  }
  .card-content p {
    margin: 0;
  }
</style>
