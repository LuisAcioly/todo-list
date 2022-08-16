<template>
    <div class="list-element">
        <div class="circle">
            <div class="icon">
                <font-awesome-icon :icon="['fa', 'check']" size="lg"/>
            </div>
        </div>
        <h1>This is a unconcluded list element</h1>
    </div>
</template>

<script>
    export default {
        name: "UnconcludedListElementComponent"
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');

    .list-element{
        color: #fff;
        background-color: #2A2A2A;
        border-radius: 5px;
        padding-left: 2vw;
        font-size: 10px;
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
      width: 20px;
      height: 20px;
      -webkit-border-radius: 25px;
      -moz-border-radius: 25px;
      border-radius: 25px;
      border-color: #fff;
      border-style: solid;
      margin-right: 1vw;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .circle:hover {
        cursor: pointer;
    }

    .icon {
        display: none;
    }

    .circle:hover  .icon {
        display: block;
    }

</style>