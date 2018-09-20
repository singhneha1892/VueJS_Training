<template>
    <div class="container">
          
        <form>
            <hr>
            <div class="row">
                <div>
                <div class="form-group">
                            <label>First Name</label>
                            <input type="text" class="form-control" v-model="fname">
                        </div><br>
                        <div class="form-group">
                            <label>Last Name</label>
                            <input type="text" class="form-control" v-model="lname">
                        </div><br>  
                     <div class="form-group">
                        <label>Mail</label>
                        <input type="text" class="form-control" v-model="email">
                    </div>
                    <br>
                    <div class="form-group">
                        <label>Password</label>
                        <input type="password" class="form-control" v-model="password">
                    </div>
                    <br>
                    <div class="form-group">
                        <label>Save in database?</label>

                        <label class="radio-inline">
                            <input type="radio" value="Yes" v-model="radio"> Yes
                        </label>
                        <label class="radio-inline">
                            <input type="radio" value="No" v-model="radio"> No
                        </label>
                    </div>
                   <button
                            type="submit"
                            @click.prevent="submitdata = true"
                            class="btn btn-warning">Submit</button>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="submitdata">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <FullName>Fullname: {{fname}} {{lname}}</FullName>
                        <p>Mail: {{ email }}</p>
                        <p>Password: {{ password }}</p>
                        <p>Store in Database?: {{ storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import FullName from "./components/FullName.vue";
export default {
  components: {
    Fullname: FullName
  },
  data() {
    return {
      fName: "",
      lname: "",
      email: "",
      password: "",
      storeData: "No",
      submitdata: false
    };
  }
};
</script>

<style>
</style>