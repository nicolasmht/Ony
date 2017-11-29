<template>

    <div id="sounds">

        <!-- Grid Bootstrap -->
        <b-row>

            <!-- First column -->
            <b-col>
                <div class="sound">
                    <img src="http://placehold.it/200x160" alt="" class="icon-sound">
                    <input type="range" min="0" max="100" class="range-sound">
                </div>
            </b-col>

            <!-- Second column -->
            <b-col>
                <div class="sound">
                    <img src="http://placehold.it/200x160" alt="" class="icon-sound">
                    <input type="range" min="0" max="100" class="range-sound">
                </div>

                <div class="sound">
                    <img src="http://placehold.it/200x160" alt="" class="icon-sound">
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
        min-height: 190px;
        margin: auto;
        margin-bottom: 50px;
        /* background-color: red; */
    }

    .img-sound{
        width: 100%;
    }

    .range-sound{
        width: 100%;
        height: 3px;

        -webkit-appearance: none;
        appearance: none;
        background: #000;
        border-radius: 2px;
        outline: none;
    }

    .range-sound::-webkit-slider-thumb{
        -webkit-appearance: none;
        appearance: none;
        width: 20px;
        height: 20px;
        background: #000;
        border-radius: 10px;
        cursor: pointer;
    }

    .range-sound::-moz-range-thumb{
        width: 20px;
        height: 20px;
        background: #000;
        border-radius: 10px;
        cursor: pointer;
    }
</style>
