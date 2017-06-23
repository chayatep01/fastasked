<template>
  <div id="app" class = "container">
    <div class = "page-header">
      <h3> Hello World </h3>
      <h2> Hello World </h2>
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
let messageSaid = db.ref('Message');

export default {
  name : 'app',
  firebase: {
    Message : messageSaid
  }
}
</script>

<style>
 #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
