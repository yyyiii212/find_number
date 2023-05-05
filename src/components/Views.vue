<script>
export default {
    data() {
        return {
            num1: 1,
            num2: 100,
            num3: null,
            result: Math.floor(Math.random() * 100) + 1,
            isWin: false,
            answer: true

        }
    },
    methods: {
        cal() {
            if (this.num3 > this.result) {
                if (this.num3 < this.num2) {
                    this.num2 = this.num3;
                }
            } else if (this.num3 < this.result) {
                if (this.num3 > this.num1) {
                    this.num1 = this.num3;
                }
            } else if (this.num3 == this.result) {
                this.isWin = true;
                this.answer = false;
            }
        }
    },
    mounted() {

    },
}
</script>

<template>
    <div class="views">
        <h1 v-if="answer">猜數字</h1>
        <h1 v-if="isWin">猜對了!!!</h1>
        <div class="vi d-flex" v-if="answer">
            <p>{{ num1 }}</p>
            <p>-</p>
            <p>{{ num2 }}</p>
        </div>
        <p id="answer" v-if="isWin">{{ result }}</p>

        <input class="input" type="number" v-model="num3" v-if="answer">
        <button type="button" @click="cal" v-if="answer">Confirm</button>
    </div>
</template>

<style lang="scss" scoped>
.views {
    background-color: white;
    width: 400px;
    height: 400px;
    display: flex;
    flex-direction: column;
    // justify-content: center;
    align-items: center;
    border-radius: 50px;

    #answer {
        margin-top: 70px;
        font-size: 48px;
    }

    h1 {
        margin: 60px 30px 0 0;
        font-size: 40px;
    }

    P {
        font-size: 28px;
        margin-top: 30px;
    }

    .input {
        margin-top: 20px;
    }

    button {
        border: none;
        background-color: rgb(0, 0, 0);
        color: rgb(255, 255, 255);
        border-radius: 5px;
        transition: 0.3s;
        padding: 8px 12px;
        margin-top: 30px;

        &:hover {
            background-color: rgb(109, 208, 206);
            color: white;
        }

        &:active {
            scale: 0.95%;
        }
    }

}
</style>