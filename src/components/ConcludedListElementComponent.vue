<template>
    <div class="concluded-list-element">
        <div class="concluded-circle">
            <div class="concluded-icon">
                <font-awesome-icon :icon="['fa', 'check']" size="lg"/>
            </div>
        </div>
        <h1><strike>This is a concluded list element</strike></h1>
    </div>
</template>

<script>
    export default {
        name: "ConcludedListElementComponent"
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');

    .concluded-list-element{
        color: #919191;
        background-color: #2A2A2A;
        border-radius: 5px;
        padding-left: 2vw;
        font-size: 10px;
        display: flex;
        align-items: center;
    }

    .concluded-list-element:hover {
        background-color: #373737;
    }

    .concluded-list-element h1 {
        font-family: 'Roboto', sans-serif;
        font-weight: 300;
    }

    .concluded-circle {
      width: 20px;
      height: 20px;
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