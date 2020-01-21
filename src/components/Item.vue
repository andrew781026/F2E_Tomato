<template>
    <div class="root">
        <div class="circle"></div>
        <div class="text">The First Thing To Do Today</div>
    </div>
</template>

<script>
    export default {
        name: "item"
    }
</script>

<style scoped>

    .root{
        background-color: #fdfdfe;
        height: 60px;
        width:50vw;
        border-radius: 60px;
        display: flex;
        align-items: center;
        padding: 30px;
    }

    .circle{
        height: 30px;
        width: 30px;
        border-radius: 50%;
        border: 7px solid #d8674e;
    }

    .text{
        font-size: 50px;
        font-weight: 900;
        padding-left: 10px;
    }

</style>
