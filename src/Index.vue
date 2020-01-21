<template>
    <div id="app">
        <App/>
    </div>
</template>

<script>
    import App from './App'

    export default {
        name: 'app',
        components: {
            App // style = [ count . music . stat ]
        }
    }
</script>

<style>
    body {
        margin: 0;
        background-color: #fde4b4;
    }

    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
    }
</style>
