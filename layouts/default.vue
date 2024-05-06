<template>
<!------------------------------------------------------------------------------------------ NAVBAR ------------------------------------------------------------->
    <nav class="navbar navbar-expand-lg" style="background-color: rgb(154, 72, 231);">
  <div class="container">
    <a class="navbar-brand fw-semibold fs-3 text-white" href="/">FLOR</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav fs-5 ms-auto">
        <NuxtLink class="nav-link text-white" to="/">Home</NuxtLink>
        <NuxtLink class="nav-link text-white">About</NuxtLink>
        <NuxtLink class="nav-link text-white">Gallery</NuxtLink>
      </div>
    </div>
  </div>
</nav>  

  <main>
    <slot></slot>
  </main>
  
</template>

<style scoped></style>