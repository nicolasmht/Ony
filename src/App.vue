<template>
    <div id="app">

        <header id="header">

            <svg id="logo" data-name="Calque 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 271 219">
                <title>logo</title>
                <path class="path" d="M98.4,97.4C82.2,127.2,57,150.6,29.8,140.6c-16.4-6-22.8-21-22.8-37.4C7,60.6,44.4,23.6,67,15.6c11.6-4,21.6-1.8,27.2,4C119,30.4,113.4,69.8,98.4,97.4Zm-8.2-73c-9.8-3.6-35.2,10-54,39.2C17,93.4,16.6,127.2,30.2,133c13.2,5.6,36.8-10.4,53.6-41.2C102,58.4,101.2,28.4,90.2,24.4Z"/>
                <path class="path" d="M167.6,60.6c6.6,1,12.8,10.8,7.8,21.2-4.2,8.8-14,23.6-18.6,34-5.2,11.6-4,21,3.2,20.6,8.2-.4,18-13.6,25.6-27.6,1-1.8,2.4-1.8,3.4-.2,1.4,2.2,1,6.8-1.8,12.6-5.4,11.2-18,21.4-29.6,21.4-17,0-21-12.4-15.2-29.8C149,93.2,166.6,72,163,70.4c-2-.8-13.6,4.8-26.4,18.8-11.8,12.8-20.6,32-29.2,50.8-.8,1.8-2,2.6-3.8.8-4-4-5.2-10.6-2-20.6,4-12.6,19.4-40.4,32-59,1.4-2.2,3-2,4.2,0,3,5,2.8,11.8.6,19C147.4,70.6,161,59.6,167.6,60.6Z"/>
                <path class="path" id="path" d="M221,146.4c-11.2,26.8-25.4,59-42,65.4-3.8,1.4-7.6,1.4-11.4-4.2-4-6-8-13-4-24.8,6-18,23-30,42.8-37.8,2-4.6,4-9.6,6.2-14.4-6.2,6.4-13.8,11.6-21.8,11-14.4-1.2-14.8-15.8-10.2-29C185,99.8,194.8,80,207.8,62c1.6-2.2,3.6-2,5,0,4.8,6.4,3.6,14.8-3.8,26.6-7.2,11.6-11.6,19.8-15.4,29.2-4,9.8-3.6,16.8,1,17.2,7.8.6,17.8-12.2,28-29.6,8.6-14.8,17.2-32.8,24.2-43,1.8-2.6,3.2-3,5-1.4,2.8,3.6,4.4,12.2-.8,22.4-6,11.6-18.2,35.6-26.6,55a106.48,106.48,0,0,0,35.4-30.8c1-1.4,2.8-1.6,3.2.4.4,1.8-.2,6.4-3.6,11.6C251.6,132,237.6,139.6,221,146.4Zm-49.4,54.4c2.6,3.8,19-18,31.4-47.4C177,168.4,168,195.8,171.6,200.8Z"/>
            </svg>
            
            <!-- <h2 id="title">Click on an icon and open your ears !</h2> -->

        </header>

        <sounds></sounds>

        <background></background>

        <footer id="footer">Nicolas Michot</footer>
    </div>
</template>

<script>

    // Import Bootstrap
    import 'bootstrap/dist/css/bootstrap.min.css';

    // Import components
    import Sounds from './components/sounds'
    import Background from './components/background'

    import Logo from './assets/logo/logo.svg';

    export default {
        name: 'app',
        components: {
            Sounds,
            Background
        },
        data () {
            return {
                logo: Logo
            }
        }
    }
</script>

<style>

    @import url('https://fonts.googleapis.com/css?family=Roboto:300,400,900');

    #app{
        max-width: 720px;
        margin: auto;
        font-family: 'Roboto', sans-serif;
    }

    #header{
        padding-top: 30px;
        margin-bottom: 60px;
    }

    #logo{
        width: 200px;
        margin: auto;
        display: block;
        font-size:200px;
        font-family: SignPainter-HouseScript, SignPainter;
    }

    .path{
        stroke-width: 3;
        stroke: #fff;
        fill: transparent;
        /*animation: path 5s linear forwards;*/
    }

    /*.path:nth-of-type(1){ animation-delay: 0s; }
    .path:nth-of-type(2){ animation-delay: 1.7s; }
    .path:nth-of-type(3){ animation-delay: 4.3s; }*/

    /*@keyframes path {
        0%{ stroke-dashoffset: 1000; }
        100%{ stroke-dashoffset: 0;}
    }*/

    #title{
        margin: 0;
        text-align: center;
        font-size: 18px;
        color: #fff;
        font-weight: 300;
    }

    #footer{
        position: absolute;
        right: 0; bottom: 0; left: 0;
        width: 100%;
        color: #fff;
        text-align: center;
        font-size: 12px;
    }
</style>


