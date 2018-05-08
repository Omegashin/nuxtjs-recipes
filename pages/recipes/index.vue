<template>
<section class="recipes">
  <Recipe
  v-for="recipe in recipes"
  :key="recipe.id"
  :thumbnail="recipe.thumbnail"
  :title="recipe.title"
  :id="recipe.id"
  :previewText="recipe.previewText"
  />
</section>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
  components: {
    Recipe
  },
  asyncData () {
    return new Promise ((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "Yummy Chicken Burger",
              previewText: "A yummy burger made with real chicken!",
              thumbnail: "http://www.manathota.in/mandapeta/wp-content/uploads/2017/11/Spicy-Chipotle-Chicken-Burger-3.jpg"
            },
            {
              id: "2",
              title: "Rigatoni Pasta",
              previewText: "Delicious pasta with cherry tomato sauce!",
              thumbnail: "https://www.seriouseats.com/recipes/images/2016/08/20160827-cherry-tomato-pasta-13-1500x1125.jpg"
            }
          ]
        })
      }, 100)
    })
  }
}
</script>


<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-content: center;
  margin: 8px;
}
</style>
