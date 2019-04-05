/* eslint-disable */
<template>
    <section>
        <div class="top1">
            {{time1}}
        </div>
    </section>
</template>

<script>

export default {

    data() {
        return {
            timer: 250,
            message2: "Start",
            counter: false,
            interval: null,
            time1: null
        }
    },

    created: function () {
       this.startTimer();
    },

    methods: {
        startTimer() {
            this.interval = setInterval(this.countDown, 1000);
            // eslint-disable-next-line

            
        },
        countDown() {
            this.time1 = new Date.now();
            var options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            console.log(this.time1.toLocaleDateString('de-DE', options))
            console.log(Date.now().toLocaleString("de-DE"));
            var n = this.timer
            if (!this.counter) {
                this.counter = true;
            } else if (n > 0) {
                n = n - 1
                this.timer = n
                this.message2 = "You have " + n + "seconds left."

            } else {
                clearInterval(this.interval);
                this.counter = false
                this.message2 = "Your time is up!"
            }
        }
    }


}
</script>

<style scoped>

section {
    width: 100%;
    padding-top: 25px;

    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    background-color: rgb(71, 193, 206);
}

.top1 {
    width: 48px;
    height: 48px;
    vertical-align: middle;
}


</style>
