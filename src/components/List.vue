<template>
    <div>
        <div class="single" v-bind:key="item" v-for="item in list">
            <div class="circle"></div>
            <div class="text">{{item}}</div>
            <img src="../assets/play.png">
        </div>
    </div>
</template>

<script>
    export default {
        name: "List",

        data() {
            return {
                list: [
                    'The Second Thing To Do Today',
                    'The Third Thing To Do Today',
                    'The Forth Thing To Do Today',
                ],
            }
        },
    }
</script>

<style scoped>

    .single {
        height: 60px;
        border-radius: 60px;
        display: flex;
        align-items: center;
        padding: 10px;
        width: 700px;
    }

    .circle {
        height: 30px;
        width: 30px;
        border-radius: 50%;
        border: 7px solid #d8674e;
    }

    .text {
        font-size: 30px;
        font-weight: 900;
        padding-left: 10px;
        padding-right: 20px;
        display: flex;
        flex: 1;
    }


</style>
