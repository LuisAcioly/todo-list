<template>
    <div class="concluded-list">
        <ul>
            <li v-for="task in concludedTasks" v-bind:key="task">
                <ConcludedListElementComponent :task="task" @unconclude-task="unconcludeTask" @delete-unconclude-task="deleteTask"/>
            </li>
        </ul>
    </div>
</template>

<script>
    import ConcludedListElementComponent from './ConcludedListElementComponent.vue';
    export default {
        name: "ConcludedListComponent",
        components: {ConcludedListElementComponent},
        props: {
            concludedTasks: Array,
        },
        methods: {
            unconcludeTask(event) {
               var unconcludedTask = event;
               unconcludedTask.completa = false;
               
               this.removeTask(event);

               this.$emit('send-unconclude-task', event);
            },
            addTask(task){
                this.concludedTasks.push(task)
            },
            deleteTask(event){
                this.removeTask(event);
            },
            removeTask(event){
                const index = this.concludedTasks.findIndex(task => {
                    return task.id === event.id
                })

               this.concludedTasks.splice(index, 1);
            }
        },
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');

    .concluded-list {
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

