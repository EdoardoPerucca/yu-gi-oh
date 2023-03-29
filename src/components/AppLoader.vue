<script>

export default {

    name: "AppLoader",

    data() {
        return {
        }
    },

}
</script>

<template>
    <div id="loading">
        Loading...
    </div>
</template>

<style lang="scss" scoped>
#loading {
    display: flex;
    justify-content: center;
    align-items: center;
    position: fixed;
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: black;
    color: white;
}
</style>