<template>
    <div>
        <Tomato type="count" :time="showTime"/>

        <div class="line"></div>
        <div>
            <img v-if="!timeOutRefresh" class="button" src="../assets/play.png" alt="play" height="80" @click="start">
            <img v-else class="button" src="../assets/stop.png" alt="pause" height="80" @click="pause">
        </div>
    </div>
</template>

<script>
    import Tomato from "./Tomato";

    export default {
        name: "TomatoDiv",

        components: {
            Tomato, // type = [ count . music . stat ]
        },

        created() {
            // 在 created 的時候建立 this.timer 順便設定其預設值
            this.timer = 60 * 25; // 25 : 00 = 60 * 25 seconds
        },
        updated() {
            // 讓我們可以知道組件有被更新
            // window.console.log('view updated , this.timer=', this.timer);
        },
        beforeMount() {
            // this.timeOutRefresh = window.setInterval(() => {
            //
            //     if (this.timer > 0) this.timer--;
            //     else {
            //         this.type = 'music';// type = [ count . music . stat ]
            //         window.clearInterval(this.timeOutRefresh);
            //     }
            //
            // }, 1000);
        },
        methods: {
            start() {

                if (!this.timeOutRefresh) {

                    this.timeOutRefresh = window.setInterval(() => {

                        if (this.timer > 0) this.timer--;
                        else {
                            this.type = 'music'; // type = [ count . music . stat ]
                            window.clearInterval(this.timeOutRefresh);
                        }

                    }, 1000);
                }
            },
            pause() {

                if (this.timeOutRefresh) {

                    window.clearInterval(this.timeOutRefresh);
                    this.timeOutRefresh = undefined;
                }
            }
        },
        beforeDestroy() {
            window.clearInterval(this.timeOutRefresh);
        },
        data() {
            return {
                timer: this.timer,
                timeOutRefresh: this.timeOutRefresh,
            }
        },
        computed: {
            showTime: function () { // this cannot use arrow function , or it will be undefined
                // https://stackoverflow.com/questions/50260260/vuejs-variable-is-undefined-inside-computed-only

                const time = new Date(this.timer * 1000);

                return time.getMinutes() + ":" + time.getSeconds();// timeStr.toString()
            }
        },
    }

</script>

<style scoped>

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
</style>
