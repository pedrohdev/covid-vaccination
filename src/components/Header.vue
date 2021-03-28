<template>
    <div>
        <p class="purple small-card small-card-purple" >Dados do dia: <strong class="purple">{{ day.split('-')[2] + '/' + day.split('-')[1] +'/'+ day.split('-')[0] }}</strong></p>
        <h3>Dados sobre a vacinação contra o Corona Vírus no <span class="green small-card small-card-green">Brasil</span></h3>
    </div>
</template>

<script>
export default {
    name: 'Header',
    props: {
        day: String
    }
}
</script>

<style scoped>
h3 {
    text-align: center;
    margin-top: 40px;
    color: #6c757d;
}
.green {
    color: rgb(14, 196, 57)
}
.purple {
    color: rgb(75, 49, 110)
}
p {
    text-align: center;
    font-size: .75rem;
    margin-top: 7px;
    margin-left: 5px;
    margin-right: 5px;
}
</style>