<template>
<nav>
    <v-toolbar dark>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
     <a flat href="https://blog975.herokuapp.com/">   <v-toolbar-title  class="text-uppercase font-weight-light">
            Daily<span class="text-uppercase font-weight-bold">Blog's</span>
        </v-toolbar-title></a>
        <v-spacer></v-spacer>
        <v-toolbar-items>

        </v-toolbar-items>
    </v-toolbar>

</nav>
</template>

<script>

export default{
    name:'Navbar',
    data:()=>({
        drawer:false,
        newPostDialog:false,
        newPost:{}

    }),

    methods:{

    }

}
</script>
<style>
a,a:hover,a:active,a:focus{
    text-decoration:none;
    color:inherit;

}
</style>