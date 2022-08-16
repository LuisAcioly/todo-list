<template>
    <div class="main">
        <h1 class="main-title">LISTA</h1>
        <UnconcludedListComponent :unconcludedTasks="unconcludedList" ref="unconcludedListRef" @send-conclude-task="receiveConcludeTask"/>

        <button @click='showConcludedList' class="concluded-button" v-show="concludedList.length > 0">Concluído {{concludedList.length}}</button>
        <div class="concluded" v-show="showList">
            <ConcludedListComponent :concludedTasks="concludedList" ref="concludedListRef" @send-unconclude-task="receiveUnconcludeTask"/>
        </div>
    </div>
</template>

<script>
    import ConcludedListComponent from './ConcludedListComponent.vue'
    import UnconcludedListComponent from './UnconcludedListComponent.vue'
    import Task from '../models/Task'

    export default {
        name: "ListComponent",
        components: {ConcludedListComponent, UnconcludedListComponent},

        data(){
            return {
                unconcludedList: [],
                concludedList: [],
                showList: false,
            }
        },
        created(){

            this.initArrays()
        },
        methods: {
            showConcludedList(){
                if(this.showList){
                    this.showList = false;
                }
                else{
                    this.showList = true;
                }
            },
            initArrays(){

                const tasks = [
                    new Task(1, 'item1', '01/01/2022', true),
                    new Task(2, 'item2', '01/01/2022', true),
                    new Task(3, 'item3', '01/01/2022', false),
                    new Task(4, 'item4', '01/01/2022', false),
                    new Task(5, 'item5', '01/01/2022', true),
                    new Task(6, 'item6', '01/01/2022', false),
                    new Task(7, 'item7', '01/01/2022', true)
                ]

                tasks.forEach((task) => {
                    if(task.completa){
                        this.concludedList.push(task)
                    }
                    else{
                        this.unconcludedList.push(task)
                    }
                })
            },
            receiveConcludeTask(event){
                this.$refs['concludedListRef'].addTask(event)
            },
            receiveUnconcludeTask(event){
                this.$refs['unconcludedListRef'].addTask(event)
            }
        }
    }

</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');

    .main {
        width: 60vw;
        color: #788CDE;
    }
    
    .main-title {
        font-family: 'Roboto', sans-serif;
        font-weight: bold;
    }

    .concluded-button {
        border: none;
        width: 7vw;
        border-radius: 5px;
        padding-top: 10px;
        padding-bottom: 10px;
        color: #fff;
        background-color: #2A2A2A;
        font-family: 'Roboto', sans-serif;
        font-weight: 300;
    }

    .concluded-button:hover {
        background-color: #373737;
    }

</style>