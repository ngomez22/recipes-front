<template>
  <div id="recipes">
    <div class="title has-text-centered no-recipes"
        v-if="recipes.length == 0">
      <p>No recipes available</p>
    </div>
    <div class="columns is-multiline">
      <Recipe v-for="recipe in recipes"
              v-bind:recipe="recipe"
              v-bind:key="recipe.ID"
              v-on:delete="deleteRecipe(recipe.ID)"
              v-on:edit="editRecipe(recipe)" />
    </div>
  </div>
</template>

<script>
import swal from 'sweetalert';
import Recipe from './Recipe.vue';

export default {
  name: 'recipes',
  components: {
    Recipe,
  },
  props: ['recipes'],

  methods: {
    deleteRecipe(id) {
      swal('Are you sure you want to delete this recipe?', {
        dangerMode: true,
        buttons: true,
      }).then((isConfirm) => {
        if (isConfirm) {
          this.$emit('deleteRecipe', id);
        }
      });
    },
    editRecipe(recipe) {
      this.$emit('editRecipe', recipe);
    },
  },
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.columns {
  padding-left: 4%;
}

.no-recipes {
  margin-top: 7%;
  display: flex;
  justify-content: center;
}
</style>
