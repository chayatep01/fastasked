<template>
  <div id="app" class = "container">

    <div class = "page-header">
      <nav class="navbar navbar-default" role="navigation">
  <!-- Brand and toggle get grouped for better mobile display -->
  <div class="navbar-header">
    <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1">
      <span class="sr-only">Toggle navigation</span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
    </button>
    <a class="navbar-brand" href="#">Find Chat</a>
  </div>

  <!-- Collect the nav links, forms, and other content for toggling -->
  <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">

    <div class="col-sm-3 col-md-3">
        <form class="navbar-form" role="search">
        <div class="input-group">
            <input type="text" class="form-control" placeholder="Search" name="q">
            <div class="input-group-btn">
                <button class="btn btn-default" type="submit"><i class="glyphicon glyphicon-search"></i></button>
            </div>
        </div>
        </form>
    </div>

  </div><!-- /.navbar-collapse -->
</nav>
      <img src= "./assets/logofa.png" height="80" width="80">
      <h3> Welcome to Fast-ask-community</h3>
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
