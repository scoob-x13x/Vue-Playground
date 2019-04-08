<template>
    <main>
        <CTitle
            :countertitle="this.CounterTitle"
            :counterdate="this.CounterDate"></CTitle>   
        <Counter></Counter>
    </main>
</template>

<script>
//
import Counter from "./Counter"
import CTitle from "./CTitle"

export default {
    name: 'MainView',

    components: {
      Counter,
      CTitle
    },

    data() {
        return {
            CounterTitle: "Bla",
            CounterDate: new Date('2018-05-13T00:00:00')
        }
    },


}
</script>

<style scoped>
main {
    width: 100%;
    height: 100%;


    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;

    box-shadow: 0 19px 38px rgba(0,0,0,0.30), 0 15px 12px rgba(0,0,0,0.22);
}

.app--day {
    background-image: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1));
}

.app--night {
    background-image: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1));
}

@media screen and (min-width: 450px) {
    main {
        width: 600px;
        height: 600px;

        border-radius: 20px;
    }
}
</style>
