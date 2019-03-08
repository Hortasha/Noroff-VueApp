<template>
    <div class="row">
        <div class="col-sm-12">
            <h1>My grandmas best recipes</h1>
        </div>

        <recipe-card
            v-for="(recipe, index) in recipes"
            v-bind:key="index"
            v-bind:title="recipe.title"
            v-bind:thumbnail="recipe.thumbnail"
            v-bind:link="recipe.href"
            v-bind:ingredients="recipe.ingredients"
        />
    </div>
</template>

<script>
import RecipeCard from './../mainPage/RecipeCard';

export default {
  name: 'MainPage',
  components: {
    RecipeCard
  },
  data() {
    return {
        recipes: []
    }
  },  
  created() {
      fetch("https://cors-anywhere.herokuapp.com/http://www.recipepuppy.com/api")
      .then(response => response.json())
      .then(data => {
          console.log(data);
          this.recipes = data.results;
          for(let i = 0; i < this.recipes.length; i++) {
              this.recipes[i].href = this.recipes[i].href.replace("Detail.aspx", "");
              this.recipes[i].ingredients = this.recipes[i].ingredients.split(", ");
          }
      })
      .catch(err => console.error(err));
  }
}
</script>

<style scoped>
    h1 {
        text-align: center;
        margin-bottom: 100px;
        margin-top: 50px;
    }
</style>
