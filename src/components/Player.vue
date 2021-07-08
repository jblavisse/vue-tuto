<template>
    <div class="player">
        <h2>Je suis le joueur {{pseudo}}!</h2>
    </div>
</template>

<script>
export default {
    //name: 'Player',
    props: {
        pseudo: String
    }
}
</script>

<style>

</style>