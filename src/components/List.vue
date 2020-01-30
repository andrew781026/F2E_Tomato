<template>
    <div>
        <div class="single" v-bind:key="item" v-for="item in list">
            <div class="circle"></div>
            <div class="text">{{item}}</div>
            <img src="../assets/play.png" height="50">
        </div>
        <div class="container">
            <input class="input" type="text" placeholder="Add A New Mission..."/>

            <div class="plus">
                <img src="../assets/plus.png" height="40">
            </div>
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

    .input {
        border: 3px solid #d8564a;
        border-radius: 3px;
        display: flex;
        height: 50px;
        width: 700px;
        flex: 1;
        color: #df564a;
        font-size: 30px;
        padding: 5px 15px 5px 15px; /* top right bottom left */
    }

    .input::placeholder { /* Chrome, Firefox, Opera, Safari 10.1+ */
        color: #df564a;
        opacity: 1; /* Firefox */
    }

    .container {
        position: relative;
        align-items: center;
    }

    .plus {
        position: absolute;
        right: 0;
        top: 0;
        height: 100%;
        width: 60px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-left: 3px solid #d8564a;
    }


</style>
