<template>
    <section class="hero is-info">
    <div class="hero-head">
      <nav class="navbar">
        <div class="container">
          <div id="navbarMenuHeroB" class="navbar-menu">
            <div class="navbar-end">
              <span class="navbar-item">
                <a class="button is-info is-inverted" href="http://github.com/ngomez22/recipes-front" target="_blank">
                  <span class="icon">
                    <i class="fab fa-github"></i>
                  </span>
                  <span>View source</span>
                </a>
              </span>
            </div>
          </div>
        </div>
      </nav>
    </div>

    <div class="hero-body">
      <div class="container has-text-centered">
        <p class="title">
          Recipes
        </p>
        <p class="subtitle">
          by Nicolás Gómez
        </p>
      </div>
    </div>

    <div class="hero-foot">
      <nav class="tabs is-boxed is-fullwidth">
        <div class="container">
          <ul>
            <li v-bind:class="{ 'is-active': activeTab==1 }"
                v-on:click="$emit('activateRecipes')">
              <a>View Recipes</a>
            </li>
            <li v-bind:class="{ 'is-active': activeTab==2 }"
                v-on:click="$emit('activateCreateRecipe')">
              <a>Create Recipe</a>
            </li>
          </ul>
        </div>
      </nav>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Header',
  props: ['activeTab'],
};
</script>

