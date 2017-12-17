<template>

    <div id="sounds">

        <div id="container-sounds">

           <div class="sound" v-for="sound in sounds">
               <img :src="sound.iconUrl" class="icon-sound" @click="ifActive(sound)" v-bind:class="{'soundActive': sound.active}">
               <input type="range" min="0" max="1" step="0.01" class="range-sound" v-show="sound.active" v-model="sound.howler.volume" @input="updateVolume(sound.howler)">
           </div>
        
        </div>

    </div>

</template>

<script>

    import Howler from 'Howler'

    // Import svg
    import iconCat from '../assets/icons/cat.svg'
    import iconCave from '../assets/icons/cave.svg'
    import iconFire from '../assets/icons/fire.svg'
    import iconFog from '../assets/icons/fog.svg'
    import iconForest from '../assets/icons/forest.svg'
    import iconNight from '../assets/icons/night.svg'
    import iconRain from '../assets/icons/rain.svg'
    import iconSun from '../assets/icons/sun.svg'
    import iconThunderstorm from '../assets/icons/thunderstorm.svg'
    import iconTrain from '../assets/icons/train.svg'
    import iconWater from '../assets/icons/water.svg'
    import iconWinter from '../assets/icons/winter.svg'

    // import iconSubmarine from '../assets/icons-noises/cave.svg'
    // import iconSun from '../assets/icons-noises/sun.svg'
    // 
    
    // Import sounds
    import soundCat from '../assets/noises/cat.mp3';
    import soundCave from '../assets/noises/cave.mp3';
    import soundFire from '../assets/noises/fire.mp3';
    import soundFog from '../assets/noises/fog.mp3';
    import soundForest from '../assets/noises/forest.mp3';
    import soundNight from '../assets/noises/night.mp3';
    import soundRain from '../assets/noises/rain.mp3';
    import soundSun from '../assets/noises/sun.mp3';
    import soundThunderstorm from '../assets/noises/thunderstorm.mp3';
    import soundTrain from '../assets/noises/train-01.mp3';
    import soundWater from '../assets/noises/water.mp3';
    import soundWinter from '../assets/noises/winter.mp3';
    

    export default {
        name: 'sounds',
        data () {
            return {
                sounds: [
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
                        name: 'fire', 
                        iconUrl: iconFire, 
                        active: false, 
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundFire,
                        }
                    },
                    { 
                        name: 'rain', 
                        iconUrl: iconRain,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundRain,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'thunderstorm', 
                        iconUrl: iconThunderstorm,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundThunderstorm,
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
                    },
                    { 
                        name: 'water', 
                        iconUrl: iconWater,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundWater,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'winter', 
                        iconUrl: iconWinter,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundWinter,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'cat', 
                        iconUrl: iconCat,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundCat,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'fog', 
                        iconUrl: iconFog,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundFog,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'night', 
                        iconUrl: iconNight,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundNight,
                            volume: 0.5
                        }
                    },
                    { 
                        name: 'forest', 
                        iconUrl: iconForest,
                        active: false,
                        howler: {
                            sound: null,
                            id: undefined,
                            src: soundForest,
                            volume: 0.5
                        }
                    }
                ]
            }
        },

        created() {

            // Preload the noises
            for (var i = 0; i < this.sounds.length; i++) {
                
                this.sounds[i].howler.sound = new Howl({
                    src: [this.sounds[i].howler.src],
                    volume: 0.5,
                    loop: true,
                    onend: function() {
                        console.log('Finished!');
                    }
                });
            }

        },

        methods: {

            ifActive: function (element) {

                // Change the opacity of svg
                element.active = !element.active;

                // Play or stop noise if click
                if (element.active) {

                    // Start and save id the noise
                    element.howler.id = element.howler.sound.play();
                    element.howler.sound.volume(.5, element.howler.id);
                    
                    console.log('Play');

                } else {

                    // Stop the noise
                    element.howler.sound.stop(element.howler.id);

                    // Init the range
                    element.howler.volume = 0.5;

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

<style scoped>

    #container-sounds{
        display: flex;
        flex-direction: row;
        flex-flow: row wrap;
    }

    .sound{
        position: relative;
        width: 23%;
        height: 145px;
        margin: 0 auto 10px auto;
        /*background-color: red;*/
    }

    .icon-sound{
        width: 50%;
        display: block;
        margin: auto;
        opacity: .5;
        cursor: pointer;
        /*background-color: orange;*/
    }

    .soundActive{
        opacity: 1;
    }

    .range-sound{
        width: 100%;
        height: 1px;
        margin-top: 15px;

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
