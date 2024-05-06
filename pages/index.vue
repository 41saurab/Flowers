<template>
<!------------------------------------------------------------------------------------------ HERO SECTION ------------------------------------------------------------->
<div id="carouselExampleInterval" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner" style="height: 80vh;">
    <div class="carousel-item active" data-bs-interval="10000">
      <img src="../assets/image1.jpg" class="d-block w-100" alt="image">
    </div>
    <div class="carousel-item" data-bs-interval="2000">
      <img src="../assets/image2.webp" class="d-block w-100" alt="image">
    </div>
    <div class="carousel-item">
      <img src="../assets/image3.jpg" class="d-block w-100" alt="image">
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleInterval" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleInterval" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

<!------------------------------------------------------------------------------------------ CARDS ------------------------------------------------------------->
<div  style="background-color: rgb(220, 241, 241);">
<div class="container py-5">
  <h1 class="text-center mb-5">Flowers</h1>
<div class="row">
    <div class="col-md-3">
        <div class="card" style="border: 1px solid gray">
  <img src="../assets/flower1.jpg" class="card-img-top" alt="image">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
    </div>

    <div class="col-md-3">
        <div class="card" style="border: 1px solid gray">
  <img src="../assets/flower1.jpg" class="card-img-top" alt="image">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
    </div>

    <div class="col-md-3">
        <div class="card"style="border: 1px solid gray">
  <img src="../assets/flower1.jpg" class="card-img-top" alt="image">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
    </div>

    <div class="col-md-3">
        <div class="card" style="border: 1px solid gray">
  <img src="../assets/flower1.jpg" class="card-img-top" alt="image">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
    </div>

    

    
</div>
</div>
</div>

<hr>

<!------------------------------------------------------------------------------------------ FORM ------------------------------------------------------------->


<img src="../assets/image.jpg" width="100%" class="img-fluid" alt="image">


<!------------------------------------------------------------------------------------------ Flowers ------------------------------------------------------------->

<div class="container-fluid p-5 text-center table-responsive">
  <h1 class="mb-5">Flowers around the globe</h1>
    <table class="table table-striped border table-hover fs-4">
      <thead>
        <tr>
          <th>ID</th>
          <th>Common Name</th>
          <th>Scientific Name</th>
          <th>Other Name</th>
          <th>Cycle</th>
          <th>Watering</th>
          <th>Sunlight</th>
          <th>Thumbnail</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="plant in plants" :key="plant.id">
          <td>{{ plant.id }}</td>
          <td>{{ plant.common_name }}</td>
          <td>{{ plant.scientific_name.join(', ') }}</td>
          <td>{{ plant.other_name.join(', ') }}</td>
          <td>{{ plant.cycle }}</td>
          <td>{{ plant.watering }}</td>
          <td>{{ plant.sunlight.join(', ') }}</td>
          <!-- Check if default_image exists and has thumbnail property -->
          <td>
            <img v-if="plant.default_image && plant.default_image.thumbnail" :src="plant.default_image.thumbnail" alt="Plant Thumbnail" style="max-width: 100px;">
            <span v-else>No thumbnail available</span>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
<!------------------------------------------------------------------------------------------ FORM ------------------------------------------------------------->
<hr>
<div class="container py-5">
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
  </div>
    <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Phone</label>
    <input type="number" class="form-control" id="exampleInputPhone1">
  </div>
  <div class="mb-3">
    <label for="exampleInputPhone1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1">
  </div>

  <button type="submit" class="btn btn-primary">Submit</button>
</form>
</div>

</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      plants: []
    };
  },
  created() {
    this.fetchPlants();
  },
  methods: {
    async fetchPlants() {
      try {
        const response = await axios.get('https://perenual.com/api/species-list?key=sk-fQjj66312c07104f75300');
        this.plants = response.data.data;
      } catch (error) {
        console.error('Error fetching plants:', error);
      }
    }
  }
};
</script>


<style scoped>
</style>
