
<script>
export default {
    name: "MainCharacterCard",
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="card text-center">
        <img :src="character.image" alt="">
        <h4>{{ character.name }}</h4>
    </div>
</template>

<style lang="scss" scoped>
</style>