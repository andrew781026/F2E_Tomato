<template>
    <div class="root">
        <div class="hori-leaf"></div>
        <div class="verti-leaf"></div>
        <div class="left-eye"></div>
        <div class="right-eye"></div>
        <div class="smile">
            <img src="../assets/smail.png" alt="smile">
        </div>
        <div class="timer" v-on:click="start">
            {{showTime}}
        </div>
    </div>
</template>

<script>

    export default {
        name: "Tomato",

        props: {
            type: {
                type: String,
                required: false
            },
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
            this.timeOutRefresh = window.setInterval(() => {

                if (this.timer > 0) this.timer--;
                else {
                    this.type = 'music';// type = [ count . music . stat ]
                    window.clearInterval(this.timeOutRefresh);
                }

            }, 1000);
        },
        methods: {
            start() {

                // if (!this.timeOutRefresh) this.timeOutRefresh = window.setInterval(() => this.timer++, 1000);
            }
        },
        beforeDestroy() {
            window.clearInterval(this.timeOutRefresh);
        },
        data() {
            return {
                timer: this.timer,
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
    .root {
        position: relative;
        width: 794px;
        height: 605px;
        border-radius: 50% 50%;
        background: #D9564A;
        box-shadow: 0px 3px 6px #00000029;
    }

    .hori-leaf {
        position: absolute;
        top: 0;
        left: 50%;
        width: 226px;
        height: 53px;
        border-radius: 50% 50%;
        transform: translate(-50%, -50%);
        background: #858C51;
    }

    .verti-leaf {
        position: absolute;
        top: 0;
        left: 50%;
        width: 71px;
        height: 136px;
        border-radius: 50% 50%;
        transform: translate(-50%, -50%);
        background: #858C51;
    }

    .left-eye {
        position: absolute;
        top: 10%;
        left: 30%;
        width: 50px;
        height: 50px;
        border-radius: 100%;
        background: #2e2e2e;
    }

    .right-eye {
        position: absolute;
        top: 10%;
        right: 30%;
        width: 50px;
        height: 50px;
        border-radius: 100%;
        background: #2e2e2e;
    }

    .smile {
        position: absolute;
        top: 25%;
        left: 50%;
        transform: translate(-50%, 0);
    }

    .timer {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -25%);
        font-size: 150px;
        font-weight: 900;
        color: #f8f9f9;
    }
</style>
