<template>
    <section class="recipes">
        <Recipe 
            v-for="recipe in recipes"
            :key="recipe.id"
            :thumbnail="recipe.thumbnail"
            :title="recipe.title"
            :id="recipe.id"
            :previewText="recipe.previewText"/>
    </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
    components: {
        Recipe
    },
    asyncData() {
        new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id: "1",
                            title: "Pizza",
                            previewText: "Delicious Pizza",
                            thumbnail: "https://post.healthline.com/wp-content/uploads/2020/07/pizza-beer-1200x628-facebook-1200x628.jpg"
                        },
                        {
                            id: "2",
                            title: "Pasta",
                            previewText: "Tasty Pasta",
                            thumbnail: "https://www.zegrahm.com/sites/zeg/files/styles/panopoly_image_original/public/pasta.jpg?t=1JeOaT&itok=eZRuyk0X"
                        }
                    ]
                })
            }, 1500)
        })
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