<template>
    <div class="filter">
        <div class="item" @click="filter('Male')">
            Male
        </div>

        <div class="item" @click="filter('Female')">
            Female
        </div>
        
    </div>

</template>

<script>
import { useStore } from 'vuex'
export default {
    setup() {
        const store = useStore()

        const filter = ((gender) => {
            store.dispatch('filterByGender', gender)
        })

        return {
            filter
        }
    }
}
</script>


<style lang="scss">

.filter {
  width: 400px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  border-radius: 10px;
  overflow: hidden;
  .item {
    padding: 1rem 0.5rem;
    background-color: var(--background-card);
    text-align: center;
    cursor: pointer;
    &:hover {
      color: var(--text-orange);
    }
  }
}

:root {
    --background-body: #24282F;
    --background-card: #3C3E44;
    --text-white: #FFFFFF;
    --text-gray: #c0c0c0;
    --text-orange: #FF9800;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    background-color: var(--background-body);

    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

}

h1 {
    margin-bottom: 3rem;
    text-align: center;
}

.container {
    width: 980px;
    max-width: 90%;
    margin: 5rem auto;
}

img {
    width: 100%;
}
</style>
