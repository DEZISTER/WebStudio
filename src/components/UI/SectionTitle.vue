<template>
    <h2 class="section-title"><slot></slot></h2>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.section-title {
    text-align: center;
    color: $main-text-color;
    @include font-styles(700, 28px, 32.81px);
    margin: auto auto 30px;

    
    @media screen and (min-width: 1200px) {
        @include font-styles(700, 36px, 42px);
        margin-bottom: 50px;
    }
}
</style>