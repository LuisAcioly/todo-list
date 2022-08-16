<template>
    <div class="main">
        <h1 class="main-title">LISTA</h1>
        <UnconcludedListComponent v-if="unconcludedCount > 0"/>

        <button @click='showConcludedList' class="concluded-button" v-if="concludedCount > 0">Concluído {{concludedCount}}</button>
        <div class="concluded" v-if="showList">
            <ConcludedListComponent/>
        </div>
    </div>
    
</template>

<script>
    import ConcludedListComponent from './ConcludedListComponent.vue'
    import UnconcludedListComponent from './UnconcludedListComponent.vue'

    export default {
        name: "ListComponent",
        components: {ConcludedListComponent, UnconcludedListComponent},

        data(){
            return {
                unconcludedCount: 4,
                concludedCount: 10,
                showList: false,
            }
        },
        methods: {
            showConcludedList(){
                if(this.showList){
                    this.showList = false;
                }
                else{
                    this.showList = true;
                }
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