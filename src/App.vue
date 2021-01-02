<template>
  <v-app >
  <Navbar :dialog="dialog"/>
  <v-main>
    <Dashboard :posts="posts" />
  </v-main>
  <v-btn x-large icon dark class="grey darken-4" float @click="toggleDialog()" absolute bottom right><v-icon large>mdi-plus</v-icon></v-btn>

        <v-dialog v-model="dialog" width="50%" :fullscreen="$vuetify.breakpoint.xsOnly">

        <v-card>
          <v-sheet dark class="grey darken-4"> <v-card-title >New Post</v-card-title></v-sheet>
          <v-card-text>
            <form action="https://blog975.herokuapp.com/api/post/new" method="post" >
            <v-text-field label="Title" name="title"></v-text-field>

            <v-textarea label="Content" name="content"></v-textarea>

           <v-text-field label="Author" name="author"></v-text-field>

            <input type="submit" style="color:white;background:cornflowerblue;padding:10px;border-radius:5px;">

            </form >
          </v-card-text>

        </v-card>
  </v-dialog>

  </v-app>
</template>

<script>
import axios from 'axios'
import Navbar from './components/Navbar.vue'
import Dashboard from './components/Dashboard.vue'

export default {

  name: 'App',

  components: {
    Navbar,
    Dashboard

  },

  data(){
    return{
      posts:[],
      dialog:false,
      title:"",
      author:"",
      content:""
    }
  },
  mounted(){

      axios.get("https://blog975.herokuapp.com/api/posts/all")
      .then(data=>{this.posts=data.data.result})
       .catch(err=>console.log(err))
  },
  methods:{
    toggleDialog(){
      return this.dialog=true
    }
  }
};
</script>
