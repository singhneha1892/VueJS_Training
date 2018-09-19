<template>
    <div class="container">
    <div class="row">
            <div class="col-xs-12 col-sm-6">
                <ul class="list-group">
                    <li @click="displayComponent = 'projectComponent'+index"
                            style="cursor: pointer"
                            class="list-group-item"
                            v-for="index in 5"
                            v-bind:key="index">
                        Project #{{ index }}
                    </li>
                </ul>
            </div>
        </div>
        <hr>
        <component :is="displayComponent"></component>
        
    </div>
</template>

<script>
import DefaultComponent from "./components/DefaultComponent.vue";
import projectComponent1 from "./components/projectComponent1.vue";
import projectComponent2 from "./components/projectComponent2.vue";
import projectComponent3 from "./components/projectComponent3.vue";
import projectComponent4 from "./components/projectComponent4.vue";
import projectComponent5 from "./components/projectComponent5.vue";


export default {
  data: function() {
    return {
      displayComponent: "DefaultComponent"
    };
  },
  components: {
    DefaultComponent: DefaultComponent,
    projectComponent1: projectComponent1,
    projectComponent2: projectComponent2,
    projectComponent3: projectComponent3,
    projectComponent4: projectComponent4,
    projectComponent5: projectComponent5
  }
};
</script>

<style>
/* h1 {
        color: orange;
    } */
</style>
