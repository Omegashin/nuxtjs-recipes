<template>
<section class="single-recipe">
    <h1>{{recipe.title}}</h1>
    <div>
        <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{recipe.descriptionText}}</p>
</section>
</template>

<script scoped>
export default {
  asyncData (context) {
    return new Promise ((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Yummy Chicken Burger",
              previewText: "A yummy burger made with real chicken!",
              descriptionText: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto necessitatibus odit, modi laboriosam quia tempora ut consequatur molestiae deleniti, nihil possimus facilis nostrum fugiat perferendis nesciunt autem dignissimos rem? Ipsa.",
              thumbnail: "http://www.manathota.in/mandapeta/wp-content/uploads/2017/11/Spicy-Chipotle-Chicken-Burger-3.jpg"
            },
            {
              id: "2",
              title: "Rigatoni Pasta",
              previewText: "Delicious pasta with cherry tomato sauce!",
              descriptionText: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Architecto necessitatibus odit, modi laboriosam quia tempora ut consequatur molestiae deleniti, nihil possimus facilis nostrum fugiat perferendis nesciunt autem dignissimos rem? Ipsa.",
              thumbnail: "https://www.seriouseats.com/recipes/images/2016/08/20160827-cherry-tomato-pasta-13-1500x1125.jpg"
            }
          ].find(el => el.id === context.params.id)
        })
      }, 100)
    })
  }
}
</script>

<style scoped>

.single-recipe {
    flex-flow: column;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}

.recipe-image {
    width: 100%;
}

</style>
