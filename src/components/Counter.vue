/* eslint-disable */
<template>
    <section>
        <div class="weather__icon">
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
            this.interval = setInterval(this.test, 1000);
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
        },

        test() {

            var countDownDate = new Date("Jan 5, 2021 15:37:25").getTime();
            // Get todays date and time
            var now = new Date().getTime();

            // Find the distance between now and the count down date
            var distance = countDownDate - now;

            // Time calculations for days, hours, minutes and seconds
            var days = Math.floor(distance / (1000 * 60 * 60 * 24));
            var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            var seconds = Math.floor((distance % (1000 * 60)) / 1000);

            // Display the result in the element with id="demo"
            var test  = days + "d " + hours + "h " + minutes + "m " + seconds + "s ";

            this.time1 = test;


        }
    }


}
</script>

<style scoped>

section {
    display: flex;
    flex-direction: row;
    align-items: center;
    background-color: rgb(71, 193, 206);
}

.weather__icon {
    width: 12em;
    padding-bottom: 9em;
}
</style>
