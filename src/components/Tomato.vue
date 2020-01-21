<template>
    <div class="root">
        <div class="hori-leaf"></div>
        <div class="verti-leaf"></div>
        <div class="left-eye"></div>
        <div class="right-eye"></div>
        <div class="smile">
            <img src="../assets/smail.png" alt="smile">
        </div>
        <div class="timer" v-on:click="count">
            {{timer}}
        </div>
    </div>
</template>

<script>

    export default {
        name: "Tomato",

        created() {
            // 在 created 的時候才建立 penguine 順便設值為 0
            this.timer = 0;
        },
        updated() {
            // 讓我們可以知道組件有被更新
            window.console.log('view updated , this.timer=', this.timer);
        },
        beforeMount() {
            this.timeOutRefresh = window.setInterval(() => this.timer++, 1000);
        },
        methods: {
            count() {

                if (!this.timeOutRefresh) this.timeOutRefresh = window.setInterval(() => this.timer++, 1000);
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
