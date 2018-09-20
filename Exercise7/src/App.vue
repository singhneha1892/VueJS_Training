<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
                <p> 1. Pass some text to the 3 components but not using props </p>
                <Orange>{{dataForOrangeComponent}}</Orange>
                <Black>{{dataForBlackComponent}}</Black>
                <Red>{{dataForRedComponent}}</Red>

                <p> 2. Dynamically switching the components using buttons </p>
                <br>
                <button class="btn btn-default" @click="displayComp='Orange'">Load Orange Template</button>
                <button class="btn btn-default" @click="displayComp='Black'">Load Black Template</button>
                <button class="btn btn-default" @click="displayComp='Red'">Load Red Template</button>
                <hr>
                    <component v-bind:is="displayComp"></component>
            </div>
        </div>
    </div>
</template>

<script>
    import Orange from './components/Orange.vue';
    import Black from './components/Black.vue';
    import Red from './components/Red.vue';
    export default {
        components: {
            Orange: Orange,
            Black: Black,
            Red: Red
        },
        data: function(){
            return{
                dataForOrangeComponent: 'some text from parent to orange component',
                dataForBlackComponent: 'some text from parent to black component',
                dataForRedComponent: 'some text from parent to red component',
                displayComp: ''
            }
        }
    }
</script>

<style>
</style>