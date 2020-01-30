<template>
    <div class="root">
        <div class="recent">Recently completed--</div>
        <div class="more">MORE</div>

        <div class="second">
            <img src="../assets/checked.png" alt="checked">
            <span class="font">The Completed Thing To Do Today</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Info"
    }
</script>

<style scoped>

    .root {
        position: relative;
        background-color: #fdf1d9;
        width: 720px;
        height: 120px;
        border-radius: 1px;
    }

    .recent {
        position: absolute;
        left: 10px;
        top: 10px;
    }

    .more {
        position: absolute;
        right: 10px;
        top: 10px;
        font-family: 'Microsoft JhengHei', serif;
        font-weight: 900;
    }

    .second{
        position: absolute;
        left: 20px;
        top: 50px;
        display: flex;
        align-items:center;
    }

    .font{
        font-size: x-large;
        font-family: 'Microsoft JhengHei', serif;
        font-weight: 900;
        margin-left: 10px;
    }
</style>
