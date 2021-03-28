<template>
    <div class="parent-cards">
        <div class="statics-card red-card">
            <p class="red">Doses aplicadas</p>
            <h1 class="total red">{{vaccination.total_vaccinations.toLocaleString()}}</h1>
        </div>
        <div class="statics-card blue-card">
            <p class="blue">Pessoas vacinadas <br> (1ª dose)</p>
            <h1 class="total blue">{{vaccination.people_vaccinated.toLocaleString()}}</h1>
        </div>
        <div class="statics-card green-card">
            <p class="green">Pessoas vacinadas <br> (2ª dose)</p>
            <h1 class="total green">{{vaccination.people_fully_vaccinated.toLocaleString()}}</h1>
        </div>
        <div class="statics-card gray-card">
            <p class="gray">Vacinações por dia</p>
            <h1 class="total gray">{{vaccination.daily_vaccinations.toLocaleString()}}</h1>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Statistics',
    props: {
        vaccination: {}
    }
}
</script>

<style scoped>
    .parent-cards {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        padding-left: 20px;
        margin-top: 40px;
        margin-bottom: 50px;
    }
    .statics-card {
        border-radius: 5px;
        cursor: pointer;
        z-index: 10;
        padding-bottom: 10px;
        margin-right: 20px;
        transition: 1s;
        padding: 10px;
    }
    .red {
        color: #fe0739;
        text-align: center;
    }

    .blue {
        color: #2c07fe;
        text-align: center;
    }
    .red-card:hover {
        background: rgba(255, 0, 0, 0.2);
    }
    .blue-card:hover {
        background: rgba(40, 83, 201, 0.2);
    }
    .total {
        font-weight: bolder;
        margin-top: 0;
    }
    .green {
        color: rgb(0, 255, 0);
        text-align: center;
    }
    .green-card:hover {
        background: rgba(0, 255, 0, 0.2);
    }
    .gray-card:hover {
        background: rgba(136, 136, 136, 0.2);
    }
    .gray {
        color: #acacac;
        text-align: center;
    }
    @media screen and (max-width: 768px) {
        .parent-cards {
            grid-template-columns: repeat(1, 1fr);
            padding: 0;
        }
        .statics-card {
            margin-right: 0;
            margin-bottom: 10px;
        }
    }
</style>