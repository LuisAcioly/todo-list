<template>
    <main>
        <ListComponent/>
    </main>
</template>

<script>
    import ListComponent from './ListComponent.vue';
    import ConcludedListElementComponent from './ConcludedListElementComponent.vue';
    import UnconcludedListComponent from './UnconcludedListComponent.vue'

    export default {
        name: "ToDoListComponent",
        components: {ListComponent, ConcludedListElementComponent, UnconcludedListComponent},
        data(){
            return {
                count: 5,
            }
        }
    }
</script>

<style>
    main {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        background-color: #1C1C1C;
        padding: 0;
        flex-direction: column;
    }

</style>