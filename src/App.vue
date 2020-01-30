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
        <div class="little-icon-1">
            <LittleIcon type="tomato" />
        </div>
        <div class="little-icon-2">
            <LittleIcon type="music" />
        </div>
        <div class="little-icon-3">
            <LittleIcon type="stats" />
        </div>
    </div>
</template>

<script>
    import Tomato from './components/Tomato'
    import Item from './components/Item'
    import List from './components/List'
    import LittleIcon from './components/LittleIcon'

    export default {
        name: 'app',
        components: {
            Tomato, // type = [ count . music . stat ]
            Item,
            List,
            LittleIcon,  // type = tomato . music . stats
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

    .little-icon-1{
        position: fixed;
        top: 30px;
        right: 0;
        background-color: #fdfdfe;
        padding: 5px 30px 5px 15px; /* top right bottom left */
        border-top-left-radius: 50px;
        border-bottom-left-radius: 50px;
    }

    .little-icon-2{
        position: fixed;
        top: 110px;
        right: 0;
        background-color: #fdfdfe;
        padding: 5px 30px 5px 15px; /* top right bottom left */
        border-top-left-radius: 50px;
        border-bottom-left-radius: 50px;
    }

    .little-icon-3{
        position: fixed;
        top: 190px;
        right: 0;
        background-color: #fdfdfe;
        padding: 5px 30px 5px 15px; /* top right bottom left */
        border-top-left-radius: 50px;
        border-bottom-left-radius: 50px;
    }
</style>
