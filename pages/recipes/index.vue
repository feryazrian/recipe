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

    <!-- <article class="recipe">
      <div
        class="thumbnail"
        style="background-image: url('https://i5.walmartimages.com/asr/a9409438-408f-4945-b576-3debe927bbbb_1.4b01cf95cfdcfff6d730483d926e9949.jpeg')"
      ></div>
      <h1>Title</h1>
      <p>Happy Good-Day</p>
    </article>-->
  </section>
</template>

<script>
import Recipe from "@/components/Recipe";
import { resolve, reject } from "q";
export default {
  components: {
    Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "God of War",
              previewText: "Awesome PS4 Game",
              thumbnail:
                "https://media.gamestop.com/i/gamestop/10131619/God-of-War"
            },
            {
              id: "2",
              title: "Fortnite",
              previewText: "Awesome PS4 Game",
              thumbnail:
                "https://i5.walmartimages.com/asr/a9409438-408f-4945-b576-3debe927bbbb_1.4b01cf95cfdcfff6d730483d926e9949.jpeg"
            }
          ]
        });
      }, 1500);
    });
  }
};
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
