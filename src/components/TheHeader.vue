<template>

    <header class = "header">
        <h1 class="title">
            <slot name="title" />
        </h1>
        <div class="description">
            <slot name="description" />
        </div>

        <div class="content">
            <slot />
        </div>
    </header>
</template>

<script>
    export default{
        mounted() {
            console.log(this.$slots);
        },
        beforeUnmount() {
            // Destruir as nossas libs
            // Eventos
            // Listeners
            console.log("beforeUnmount");
    },
        unmounted() {
            console.log("unmounted");
    },
    methods: {
        resize($evt){
            console.log($evt)
        }
    },
    }
</script>

<style>
    .header{
        background: #000;
        color: #fff;
    }
</style>