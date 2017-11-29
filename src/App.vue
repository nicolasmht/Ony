<template>
    <div id="app">

        <header id="header">
            <h1 id="title">Relax</h1>
            <!-- <p id="subTitle">Mix different sounds and create your perfect environment.</p> -->
        </header>

        <sounds></sounds>

        <background></background>
    </div>
</template>

<script>

    // Import Bootstrap
    import 'bootstrap/dist/css/bootstrap.css'
    import 'bootstrap-vue/dist/bootstrap-vue.css'

    // Import components
    import Sounds from './components/sounds'
    import Background from './components/background'

    export default {
        name: 'app',
        components: {
            Sounds,
            Background
        }
    }
</script>

<style>

    @import url('https://fonts.googleapis.com/css?family=Roboto:300,400,900');

    #app{
        width: 720px;
        margin: auto;
        font-family: 'Roboto', sans-serif;
    }

    #header{
        padding-top: 50px;
        margin-bottom: 100px;
    }

    #title{
        text-align: center;
        font-size: 36px;
        color: #fff;
        font-weight: 300;
    }

    #subTitle{
        text-align: center;
        font-size: 18px;
        color: #fff;
        font-weight: 300;
    }
</style>


