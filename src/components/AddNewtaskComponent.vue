<template>
    <div class="new-task-element">
        <div class="task">
            <button @click="submit" class="add-circle">
                <div class="add-icon">
                    <font-awesome-icon :icon="['fa', 'plus']" size="lg"/>
                </div>
            </button>
            <input type="text" name="task-name" id="task-name" placeholder="Adicionar uma tarefa" class="task-input" v-model="taskName">
        </div>
        <input type="date" name="task-date" id="task-date" v-model="taskDate">
    </div>
</template>

<script>
    import Task from '../models/Task';
    export default {
        name: "AddNewtaskComponent",
        emits: ['new-task'],
        data(){
            return {
                taskName: '',
                taskDate: '',
            }
        },
        methods: {
            submit(){

                if(this.taskName !== '' && this.taskDate != ''){
                    const newtask = new Task(1, this.taskName, this.taskDate, false);

                    this.$emit('new-task', newtask);
                }
            }
        }
    }
</script>

<style>
    .new-task-element {
        color: #788CDE;
        padding-top: 1.1vh;
        padding-bottom: 1.1vh;
        background-color: #2A2A2A;
        border-radius: 5px;
        padding-left: 2vw;
        padding-right: 2vw;
        display: flex;
        align-items: center;
        justify-content: space-between;
        bottom: 0;
    }

    .task-input {
        font-size: 23px;
        background-color: transparent;
        border: none;
        outline:none;
        color: #788CDE;
    }

    .task-input::placeholder {
        color: #788CDE;
    }

    .task-input:active{
        border: none;
        outline:none;
    }


    [type="date"] {
        background-color: transparent;
        border: none;
        color: #fff;
        font-family: 'Roboto', sans-serif;
        font-size: 15px;
        display: flex;
        align-items: center;
    }

    [type="date"]::-webkit-calendar-picker-indicator {
        filter: invert(1);
    }

    .add-circle {
        width: 25px;
        height: 25px;
        -webkit-border-radius: 25px;
        -moz-border-radius: 25px;
        border-radius: 25px;
        border-color: #788CDE;
        border-style: solid;
        margin-right: 1vw;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: transparent;
    }

    .add-circle:hover {
        cursor: pointer;
    }

    .add-icon {
        color: #788CDE;
    }
</style>