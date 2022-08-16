<template>
    <div class="unconcluded-list">
        <ul>
            <li v-for="task in unconcludedTasks" v-bind:key="task">
                <UnconcludedListElementComponent  :task="task" @conclude-task="concludeTask" @delete-conclude-task="deleteTask"/>
            </li>
        </ul>
    </div>
</template>

<script>
    import UnconcludedListElementComponent from '../UnconcludedList/UnconcludedListElementComponent.vue';
    export default {
        name: "UnconcludedListComponent",
        components: {UnconcludedListElementComponent},
        emits: ['send-conclude-task'],
        props:{
            unconcludedTasks: Array,
        },
        methods: {
            concludeTask(event) {
               var concludedTask = event;
               concludedTask.completa = true;

              this.removeTask(event);

               this.$emit('send-conclude-task', event);
            },
            addTask(task){
                this.unconcludedTasks.push(task)
            },
            deleteTask(event){
                this.removeTask(event);
            },
            removeTask(event){
                const index = this.unconcludedTasks.findIndex(task => {
                    return task.id === event.id
                })

               this.unconcludedTasks.splice(index, 1);
            }
        },
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

