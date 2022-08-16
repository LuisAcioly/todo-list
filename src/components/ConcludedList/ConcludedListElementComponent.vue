<template>
    <div class="concluded-list-element">
        <div class="task">
            <button class="concluded-circle" @click="$emit('unconclude-task', task)">
                <div class="concluded-icon">
                    <font-awesome-icon :icon="['fa', 'check']" size="lg"/>
                </div>
            </button>
            <h1>{{task.descricao}} - {{data.getDate()+'/' + (data.getMonth()+1) + '/'+data.getFullYear()}}</h1>
        </div>
        <button @click="$emit('delete-unconclude-task', task)" class="delete-button">
            <div class="delete-icon">
                <font-awesome-icon :icon="['fa', 'trash-can']" size="lg" />
            </div>
        </button>
    </div>
</template>

<script>

    import Task from '../../models/Task';

    export default {
        name: "ConcludedListElementComponent",
        emits: ['unconclude-task', 'delete-unconclude-task'],
        props: {
            task: Task,
        },
        data() {
            return {
                data: new Date(this.task.prazo),
            }
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');

    .concluded-list-element{
        color: #919191;
        background-color: #2A2A2A;
        border-radius: 5px;
        padding-left: 2vw;
        padding-right: 2vw;
        font-size: 10px;
        display: flex;
        align-items: center;
        text-decoration: line-through;
        justify-content: space-between;
    }

    .concluded-list-element:hover {
        background-color: #373737;
    }

    .concluded-list-element h1 {
        font-family: 'Roboto', sans-serif;
        font-weight: 300;
    }

    .concluded-circle {
      width: 25px;
      height: 25px;
      -webkit-border-radius: 25px;
      -moz-border-radius: 25px;
      border-radius: 25px;
      border-color: #788CDE;
      border-style: solid;
      background-color: #788CDE;
      margin-right: 1vw;
      display: flex;
      justify-content: center;
      align-items: center;
      color: #2A2A2A;
    }


</style>