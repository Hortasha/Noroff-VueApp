<template>
    <div class="col-sm-4 recipeCard">
        <div class="card">
            <img class="card-img" v-bind:src="thumbnail" alt="Recipe Thumbnail">
            <div class="card-body">
                <h5>{{title}}</h5>
                <ul>
                    <li
                        v-for="(ingredient, index) in ingredients"
                        v-bind:key="index"
                    >{{ingredient}}</li>
                </ul>

                <a v-bind:href="link">Here</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'RecipeCard',
  props: {
      title: String,
      thumbnail: String,
      link: String,
      ingredients: Array
  }
}
</script>

<style scoped>
.recipeCard {
    padding-bottom: 40px;
}
.card-img {
    height: auto;
}
</style>