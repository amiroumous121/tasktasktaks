<template>
  <div>
    <button @click="addRecipe">Add Recipe</button>

    <div class="recipes">
      <RecipeItem v-for="recipe in recipes" :key="recipe.id" :recipe="recipe" />

      <button v-for="recipe in recipes" @click="deleteRecipe(recipe.id)">
        Delete {{ recipe.title }}
      </button>
    </div>
  </div>
</template>

<script>
import RecipeItem from "./RecipeItem.vue";

export default {
  props: ["recipes", "addRecipe", "deleteRecipe"],

  methods: {
    addRecipe() {
      this.$emit("addRecipe");
    },

    deleteRecipe(id) {
      this.$emit("deleteRecipe", id);
    },
  },
};
</script>

<style>
/* styles */
</style>
