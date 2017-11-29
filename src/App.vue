<template>
    <div id="app">

        <header id="header">
            <h1 id="title">Relax</h1>
            <p id="subTitle">Mix different sounds and create your perfect environment.</p>
        </header>

        <sounds></sounds>

    </div>
</template>

<script>

    // Import Bootstrap
    import 'bootstrap/dist/css/bootstrap.css'
    import 'bootstrap-vue/dist/bootstrap-vue.css'

    // Import components
    import Sounds from './components/sounds'

    export default {
        name: 'app',
        components: {
            Sounds
        }
    }
</script>

<style>

    @import url('https://fonts.googleapis.com/css?family=Roboto:400,900');

    #app{
        position: relative;
        width: 720px;
        margin: auto;
        font-family: 'Roboto', sans-serif;
        background-color: rgba(255, 0, 0, .1);
    }

    #header{
        padding-top: 25px;
        margin-bottom: 50px;
    }

    #title{
        text-align: center;
        font-size: 32px;
        color: #444
    }

    #subTitle{
        text-align: center;
        color: #666;
    }
</style>


