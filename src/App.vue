<template>
    <div>
        <div class="say">
            <Item/>
        </div>
        <div class="list">
            <List/>
            <Info/>
        </div>
        <div class="tomato">
            <Tomato type="count"/>

            <div class="line"></div>
            <div>
                <img class="button" src="./assets/play.png" alt="play" height="80">
                <img class="button" src="./assets/stop.png" alt="play" height="80">
            </div>
        </div>
        <div class="little-icon">
            <div v-for="(item, index) in ['tomato','music']" :key="index">
                <LittleIcon :type="item"/>
                <div class="padding"></div>
            </div>
            <LittleIcon type="stats" :class="{ active: true }"/>
        </div>

    </div>
</template>

<script>
    import Tomato from './components/Tomato'
    import Item from './components/Item'
    import List from './components/List'
    import LittleIcon from './components/LittleIcon'
    import Info from './components/Info'

    export default {
        name: 'app',
        components: {
            Tomato, // type = [ count . music . stat ]
            Item,
            List,
            LittleIcon,  // type = tomato . music . stats
            Info,
        }
    }
</script>

<style scoped>

    .tomato {
        position: fixed;
        top: 180px;
        right: 150px;
    }

    .line {
        margin-top: 30px;
        min-height: 10px;
        background-color: #fdfdfe;
        border-radius: 10px;
        width: 115%;
        transform: translateX(-6.5%);
    }

    .button {
        margin: 10px;
    }

    .say {
        position: fixed;
        top: 100px;
        left: 100px;
    }

    .list {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        min-height: calc(100vh - 270px);
        position: fixed;
        top: 250px;
        left: 130px;
    }

    .little-icon {
        position: fixed;
        top: 30px;
        right: 0;
    }

    .padding {
        min-height: 10px;
    }

</style>
