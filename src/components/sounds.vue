<template>

    <div id="sounds">

        <!-- Grid Bootstrap -->
        <b-row>

            <!-- First column -->
            <b-col>
                <div class="sound">
                    <img src="../assets/icons-noise/rain.png" alt="" class="icon-sound">
                    <input type="range" min="0" max="100" class="range-sound">
                </div>

                <div class="sound">
                    <img src="../assets/icons-noise/forest.png" alt="" class="icon-sound">
                    <input type="range" min="0" max="100" class="range-sound">
                </div>
            </b-col>

            <!-- Second column -->
            <b-col>
                <div class="sound">
                    <img src="../assets/icons-noise/thunderstorm.png" alt="" class="icon-sound">
                    <input type="range" min="0" max="100" class="range-sound">
                </div>

                <div class="sound">
                    <img src="../assets/icons-noise/wind.png" alt="" class="icon-sound">
                    <input type="range" min="0" max="100" class="range-sound">
                </div>
            </b-col>

        </b-row>
    </div>

</template>

<script>
    export default {
        name: 'sounds'
    }
</script>

<style>
    .sound{
        width: 200px;
        margin: auto;
        margin-bottom: 50px;
    }

    .icon-sound{
        width: 120px;
        display: block;
        margin: auto auto 10px;
    }

    .range-sound{
        width: 100%;
        height: 2px;

        -webkit-appearance: none;
        appearance: none;
        background: #fff;
        border-radius: 1px;
        outline: none;
    }

    .range-sound::-webkit-slider-thumb{
        -webkit-appearance: none;
        appearance: none;
        width: 20px;
        height: 20px;
        background: #fff;
        border-radius: 10px;
        cursor: pointer;
    }

    .range-sound::-moz-range-thumb{
        width: 20px;
        height: 20px;
        background: #fff;
        border-radius: 10px;
        cursor: pointer;
    }
</style>
