<template>

    <div id="background"></div>

</template>

<script>
    export default {
        name: 'background'
    }
</script>

<style scoped>

    #background{
        position: fixed;
        top: 0; right: 0; bottom: 0; left: 0;
        z-index: -1000;

        animation: animationBackground 60s infinite ease-in-out;
    }

    @keyframes animationBackground {
        0%{
            background-color: rgba(26, 188, 156,1.0);
        }

        14%{
            background-color: rgba(46, 204, 113,1.0);
        }

        28%{
            background-color: rgba(52, 152, 219,1.0);
        }

        42%{
            background-color: rgba(155, 89, 182,1.0);
        }

        56%{
            background-color: rgba(241, 196, 15,1.0);
        }

        70%{
            background-color: rgba(230, 126, 34,1.0);
        }

        84%{
            background-color: rgba(231, 76, 60,1.0);
        }

        100%{
            background-color: rgba(26, 188, 156,1.0);
        }
    }

</style>

