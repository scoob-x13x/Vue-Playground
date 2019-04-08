<template>
    <section>
        <div class="title">
            <span class="title__value">{{ countertitle }}</span>
        </div>
        <div class="title">
            <span>{{ counterdate }}</span>
        </div>
    </section>
</template>

<script>
export default {
    name: 'CTitle',

    props: {
        countertitle : {
            type: String,
            required: true
        },
        counterdate : {
            type: Date,
            required: true
        }
    }

}
</script>

<style scoped>

section {
    width: 100%;
    padding-top: 10px;
    padding-bottom: 10px;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    background-color: #444444 ;

}

.title {
    height: 50px;
    vertical-align: middle;
}

</style>


