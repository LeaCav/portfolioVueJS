<template>
    <h1>Mon portfolio</h1>
    <strong>Léa Cavalli</strong>

    <nav>
        <ul><li><a href="">Présentation</a></li>
          <li><a href="">Mon CV</a></li>
          <li><a href="">Cahier des charges</a></li>
          <li><a href="">Travail avec JavaScript</a></li>
          <li><a href="">Mon site de Tests</a></li>
          <li><a href="">Me contacter</a></li>
        </ul>
      </nav>
</template>

<style scoped>
    @font-face {
        font-family: "Giorgio";
        src: url(../assets/fonts/Giorgio-Thin.woff2), url(../assets/fonts/Giorgio-Thin.ttf);
    }
    @font-face {
        font-family: "Relief";
        src: url(../assets/fonts.ReliefSingleLineOutline-Regular.woff2), url(../assets/fonts.ReliefSingleLineOutline-Regular.ttf);
    }

*{
    background-color: #33402B ;
    color: #F2C46D;
}
h1{
    font-family: "Giorgio";
    font-size: 50px;
    margin: 10px;
}

strong{
    font-family: "Giorgio";
    font-size: 30px;
    margin: 10px;
}

ul{
    display: flex;
    justify-content: space-evenly;
}

li{
    display: flex;
    font-family: "Relief";
    font-size: 2rem;
    text-transform:uppercase;
}

a{
    padding: 5px;
    text-decoration: none
}

a:hover {
    background: rgb(242,196,109);
    background: radial-gradient(circle, rgba(242,196,109,1) 0%, rgba(51,64,43,1) 100%); 
    color: #33402B;
}


</style>

<script setup>
import Creation from '@/components/Creation.vue'
import Contact from '@/components/Contact.vue';
</script>