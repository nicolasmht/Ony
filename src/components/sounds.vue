<template>

    <div id="sounds">

       <div class="sound" v-for="sound in sounds">
           <img :src="sound.iconUrl" alt="" class="icon-sound" @click="ifActive(sound)" v-bind:class="{'soundActive': sound.active}">
           <input type="range" min="0" max="1" step="0.01" class="range-sound" v-show="sound.active" v-model="sound.howler.volume" @input="updateVolume(sound.howler)">
       </div>

    </div>

</template>

<script>

    import Howler from 'Howler'

    // Import svg
    import iconFire from '../assets/icons-noise/fire.svg'
    import iconDrizzle from '../assets/icons-noise/drizzle.svg'
    import iconFlood from '../assets/icons-noise/flood.svg'
    import iconCave from '../assets/icons-noise/cave.svg'
    import iconSubmarine from '../assets/icons-noise/submarine.svg'
    import iconSun from '../assets/icons-noise/sun.svg'
    import iconTrain from '../assets/icons-noise/train.svg'
    
    // Import sounds
    import soundFire from '../assets/sounds-noise/fire.mp3';
    import soundDrizzle from '../assets/sounds-noise/drizzle.mp3';
    import soundFlood from '../assets/sounds-noise/flood.mp3';
    import soundCave from '../assets/sounds-noise/cave.mp3';
    import soundSubmarine from '../assets/sounds-noise/submarine.mp3';
    import soundSun from '../assets/sounds-noise/sun.mp3';
    import soundTrain from '../assets/sounds-noise/train.mp3';

    export default {
        name: 'sounds',
        data () {
            return {
                sounds: [
                    { 
                        name: 'fire', 
                        iconUrl: iconFire, 
                        active: false, 
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundFire,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'wind', 
                        iconUrl: iconDrizzle,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundDrizzle,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'flood', 
                        iconUrl: iconFlood,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundFlood,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'cave', 
                        iconUrl: iconCave,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundCave,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'submarine', 
                        iconUrl: iconSubmarine,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundSubmarine,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'sun', 
                        iconUrl: iconSun,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundSun,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'train', 
                        iconUrl: iconTrain,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundTrain,
                            volume: 0.5
                        }
                    }
                ]
            }
        },

        methods: {

            ifActive: function (element) {

                // Change the opacity of svg
                element.active = !element.active;

                // Init the player Howler if not exist
                if (element.howler.sound == null) {

                    element.howler.sound = new Howl({
                        src: [element.howler.src],
                        volume: element.howler.volume,
                        loop: true
                    })
                }

                // Play or stop noise if click
                if (element.active) {

                    element.howler.id = element.howler.sound.play();
                    console.log('Play');

                } else {

                    element.howler.sound.stop(element.howler.id);
                    console.log('Stop');
                }
            },
            
            updateVolume: function (element) {
                
                // Update the volume with the new value of sounds.sound.howler.volumn
                element.sound.volume(element.volume, element.idSound);
            }
        }
    }
</script>

<style>

    #sounds{
        display: flex;
        flex-direction: row;
        flex-flow: row wrap;
    }

    .sound{
        width: 180px;
        height: 132px;
        margin: 0 30px 60px 0;
        display: block;
    }

    .icon-sound{
        width: 50%;
        display: block;
        margin: auto;
        opacity: .5;
        cursor: pointer;
    }

    .soundActive{
        opacity: 1;
    }

    .range-sound{
        width: 100%;
        height: 1px;
        margin-top: 30px;

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
