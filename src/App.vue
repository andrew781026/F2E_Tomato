<template>
    <div>
        <div class="say">
            <Item/>
        </div>
        <div class="list">
            <List/>
        </div>
        <div class="tomato">
            <Tomato type="count"/>
        </div>
    </div>
</template>

<script>
    import Tomato from './components/Tomato'
    import Item from './components/Item'
    import List from './components/List'

    export default {
        name: 'app',
        components: {
            Tomato, // style = [ count . music . stat ]
            Item,
            List,
        }
    }
</script>

<style scoped>

    .tomato {
        position: fixed;
        top: 200px;
        right: 150px;
    }

    .say {
        position: fixed;
        top: 100px;
        left: 100px;
    }

    .list{
        position: fixed;
        top: 250px;
        left: 130px;
    }
</style>
