<template>
<div>
    <section>
    <h2>Mon Curriculum Vitae</h2>
    <img src="../assets/img/cv1.png" alt="Curriculum Vitae" title="Curriculum Vitae">
</section>

<section>
    <h2>Cahier des charges</h2>
    <img src="../assets/img/cahier-des-charges.png" alt="Cahier des charges" title="Cahier des charges">
</section>

<section>
    <h2>Travail avec JavaScript</h2>
    <img src="../assets/img/js.png" alt="Dynamiser un espace commentaire" title="Dynamiser un espace commentaire">
</section>

<section>
    <h2>Mon site de tests</h2>
    <img src="../assets/img/logo.jpg" alt="Mon site de tests" title="Mon site de tests">
</section>
</div>

</template>

<style scoped>
div{
    margin-top:40px ;
    margin-bottom: 40px;
    display: flex;
}
section{
    display: flex;
    flex-direction: column;
}
section:hover{
    border: solid #33402B;
}
h2{
    font-size: 1.2rem;
}
img{
    width: 300px;
    margin: 10px;
    cursor:pointer;
}
</style>

<script setup>

</script>