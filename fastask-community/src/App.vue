<template>
  <div id="app" class = "container">

  <div class = "page-header">
      <div>
        <img src= "./assets/logofa.png" height="80" width="80">
        <h3> Welcome to Fast-ask-community</h3>
      </div>
 </div>
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4>Live chat</h4>
    </div>
    <div class="panel-body">
     <div class="table table-striped">
       <thead></thead>
       <tbody>
         <div id="body">
           <tr v-for = "send in message">
           <td> {{send.name}}  </td><td> <p>:</p> </td><td>  {{send.text}}</td>
           </tr>
         </div>

       </tbody>
     </div>
    </div>
  </div>

  <div class="panel panel-default">

    <form id="form" class="form-inline" v-on:submit.prevent="send">
      <div class="form-group">
        <label for="whosend">name :</label>
        <input type="text" id ="whosend" class="form-control" v-model="newmessage.name">
      </div>
      <div class="form-group">
        <label for="textsend">message :</label>
        <input type="text" id ="textsend" class="form-control" v-model="newmessage.text">
      </div>
      <input type="submit" class="btn btn-primary" value="send">
    </form>
  </div>

</div>


</template>

<script>
import Hello from '@/components/Hello'
import Firebase from 'firebase'
let config ={
  apiKey: "AIzaSyCOYo6cGXaa_t1OwoJ4a7m44oWovNKubuE",
  authDomain: "pwa-onlinehackathon.firebaseapp.com",
  databaseURL: "https://pwa-onlinehackathon.firebaseio.com",
  projectId: "pwa-onlinehackathon",
  storageBucket: "pwa-onlinehackathon.appspot.com",
  messagingSenderId: "414429475616"
}
let app = Firebase.initializeApp(config);
let db = app.database();
let messageSaid = db.ref('message');

export default {
  name : 'app',
  firebase: {
  message : messageSaid
  },
  data(){
    return{
      newmessage : {
        name :'',
        text :''
      }
    }
  },
  methods : {
    send :function() {
      messageSaid.push(this.newmessage)
      this.newMessage.name='';
      this.newMessage.text=''

    }

  }
}
</script>

<style>
 #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  margin-top: 60px;
}
#body{}
#inputmessage{

}
</style>
