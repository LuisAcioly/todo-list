<template>
    <div class="list-element">
        <div class="task">
            <button @click="$emit('conclude-task', task)" class="circle">
                <div class="icon">
                    <font-awesome-icon :icon="['fa', 'check']" size="lg"/>
                </div>
            </button>
        <h1>{{task.descricao}}</h1>
        </div>
        <button @click="$emit('delete-conclude-task', task)" class="delete-button">
            <div class="delete-icon">
                <font-awesome-icon :icon="['fa', 'trash-can']" size="lg" />
            </div>
        </button>
    </div>
</template>

<script>
    import Task from '../../models/Task';

    export default {
        name: "UnconcludedListElementComponent",
        emits: ['conclude-task', 'delete-conclude-task'],
        props: {
            task: Task
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');

    .list-element{
        color: #fff;
        background-color: #2A2A2A;
        border-radius: 5px;
        padding-left: 2vw;
        padding-right: 2vw;
        font-size: 10px;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .task {
        display: flex;
        align-items: center;
    }

    .list-element:hover {
        background-color: #373737;
    }

    h1 {
        font-family: 'Roboto', sans-serif;
        font-weight: 300;
    }

    .circle {
      width: 25px;
      height: 25px;
      -webkit-border-radius: 25px;
      -moz-border-radius: 25px;
      border-radius: 25px;
      border-color: #fff;
      border-style: solid;
      margin-right: 1vw;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: transparent;
    }

    .circle:hover {
        cursor: pointer;
    }

    .icon {
        display: none;
        color: #fff;
    }

    .circle:hover  .icon {
        display: block;
    }

    .delete-button {
        background-color: transparent;
        border: none;
        float: right;
    }

    .delete-button:hover{
        cursor: pointer;
    }

    .delete-icon {
        color: #F25050;
    }

</style>