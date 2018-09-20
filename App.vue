<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Directives Exercise</h1>
                <p>Build a Custom Directive which works like v-on (Listen for Events) which accepts a function as the parameter</p>
                <p>Eg - v-custom-on:click="function"</p>
                <!-- Hint - Think about native addEventListener -->
            </div>
         </div>
        <button v-custom-on:click="displayMessage" class="comp">Click </button>
    <hr>
    <div>{{message}}</div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
            message: "Button not yet clicked"
            }
        },
        methods:{
            displayMessage: function(){
                this.message = "Custom directive button clicked"
            }
        },
        directives:{
            'custom-on':{
                bind(element,binding){
                    if(binding.arg == 'click'){
                        element.addEventListener("click", function(){
                            binding.value();
                        });
                    }
                }
            }
        }
    }
</script>
