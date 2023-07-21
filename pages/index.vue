<template> 
  <div>
  <div class='title'>
  <h1> Galaxy Raiders</h1>
  </div>
  <div class='menu'>   
        <ul>
          <li> <NuxtLink to="/game"> Iniciar Partida </NuxtLink> </li>
          <li> <NuxtLink to="/leaderboard"> Placar </NuxtLink> </li>
          <li> <a v-on:click='exit()' href='#'> Sair </a> </li>

        </ul>
    

  </div>
  </div>
</template>


<style>

d1 {
  align-self:center;
  font-weight: bold;
}

ul {
  list-style-type: none;
  padding: 0;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  align-self:center;
  width: 100%;
}
li {
  margin: 0 0.5rem;
  padding: 0.25rem;
  font-size: 1.2rem;
  color:azure;
  text-align: center;
  width: 100%;
}

nav {
  padding: 0 1rem;
}

a,
a:visited {
  text-decoration: none;
  color: inherit;
  text-align: center;

}

a:hover {
  color: #00c58e;
}
/* home route and active route will show in bold as it matches / and /about */
a.nuxt-link-active {
  font-weight: bold;
}
/* exact link will show the primary color for only the exact matching link */
a.nuxt-link-exact-active {
  color: #00c58e;
}

body {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto,
    Helvetica Neue, Arial, Noto Sans, sans-serif, Apple Color Emoji,
    Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
    background-color: rgb(202, 202, 202);
  margin: 0;
}

.menu {
  margin: 5vw;
  margin-top: 1vw;
  display:flex;
  flex-direction: row;
  align-items: center;
  width: 90vw;
  border-radius:1em;
  background-color: rgb(82, 82, 82);
}
  .title{
        text-align: center;
    }
</style>

<script>
  export default{

    methods:{
      exit: ()=>{
         useFetch('exit', {
      baseURL: 'http://localhost:5000',
      method: "GET",
      initialCache: false,
      
      });
    window.location.replace("https://www.youtube.com/watch?v=dQw4w9WgXcQ");


      }
    }

    
  }
  onMounted(() => {window.onpopstate = function () {
    location.reload()
  };})
</script>
