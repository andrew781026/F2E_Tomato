<template>
    <div class="root">
        <img :src='icon.src' :alt="icon.alt">
    </div>
</template>

<script>
    import tomatoImg from "../assets/tomato.png";
    import musicImg from  "../assets/music.png";
    import statsImg from  "../assets/chart.png";

    // https://stackoverflow.com/questions/45116796/how-to-import-and-use-image-in-a-vue-single-file-component
    const iconMap = {
        tomato: {
            src: tomatoImg,
            alt: 'tomato'
        },
        music: {
            src: musicImg,
            alt: 'music'
        },
        stats: {
            src: statsImg,
            alt: 'stats'
        }
    };

    export default {
        name: "LittleIcon", // type = tomato . music . stats
        props: {
            type: String
        },
        data: function () {

            return {
                icon:  iconMap[this.type] || {}
            }
        },
    }
</script>

<style scoped>

    .root {
        height: 60px;
        width: 60px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

</style>
