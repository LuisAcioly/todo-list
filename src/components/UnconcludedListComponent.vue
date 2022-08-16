<template>
    <div class="unconcluded-list">
        <ul>
            <li v-for="item in items" v-bind:key="item">
                <UnconcludedListElementComponent />
            </li>
        </ul>
    </div>
</template>

<script>
    import UnconcludedListElementComponent from './UnconcludedListElementComponent.vue';
    export default {
        name: "UnconcludedListComponent",
        components: {UnconcludedListElementComponent},
        data(){
            return {
                items: [1, 2, 3, 4]
            }
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');

    .unconcluded-list {
        width: 100%;
    }

    ul {
        list-style: none;
        padding: 0;
    }

    li {
        margin-bottom: 0.5vh;
    }

</style>

