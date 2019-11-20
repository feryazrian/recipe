<template>
  <!-- <p>{{$route.params.id}}</p> -->
  <section class="single-recipe">
    <h1>{{recipe.title}}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title" />
    </div>
    <p>{{recipe.descriptionText}}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "God of War",
              previewText: "Awesome PS4 Game",
              descriptionText: "Only On PlayStation",
              thumbnail:
                "https://media.gamestop.com/i/gamestop/10131619/God-of-War"
            },
            {
              id: "2",
              title: "Fortnite",
              previewText: "Awesome PS4 Game",
              descriptionText: "Only On PlayStation",
              thumbnail:
                "https://i5.walmartimages.com/asr/a9409438-408f-4945-b576-3debe927bbbb_1.4b01cf95cfdcfff6d730483d926e9949.jpeg"
            }
          ].find(el => el.id === context.params.id)
        });
      }, 1500);
    });
  }
};
</script>

<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}

.recipe-image {
  width: 100%;
}
</style>
