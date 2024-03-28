<script setup>
const creation = [
    {
        title: 'Mon Curriculum Vitae',
        img: '../assets/img/icons8-fermer-la-fenêtre-100.png',
        date: 30/1/2024,
        usedTech: 'HTML5 / CSS3',
        link: 'https://github.com/LeaCav/cv-lea-cavalli/tree/main>ici</a></strong'
    },
    {
        title: 'Cahier des charges',
        img: '../assets/img/icons8-fermer-la-fenêtre-100.png',
        date: 15/2/2024,
        usedTech: 'Google doc / Inkscape / Paint 3D / Adobe color',
        link: '../views/Error.vue',
    },
    {
        title: 'Travail avec JavaScript' ,
        img: '../assets/img/icons8-fermer-la-fenêtre-100.png',
        date: 26/2/2024,
        usedTech: 'HTML 5 / CSS 3 / JavaScript',
        link: 'https://github.com/LeaCav/dynamiser-un-espace-commentaire' ,
    },
    {
        title: 'Mon site de tests',
        img: '../assets/img/icons8-fermer-la-fenêtre-100.png',
        date: 27/2/2024,
        usedTech: 'HTML 5 / CSS 3 / JavaScript / Inkscape / Adobe color',
        link: 'https://github.com/LeaCav/mon-site-de-tests',
    },
];

</script>

<template>
<div>
<button>
    <section id = "openModal1">
        <h2>Mon Curriculum Vitae</h2>
        <img src="../assets/img/cv1.png" alt="Curriculum Vitae" title="Curriculum Vitae">
    </section>
</button>

<button>
    <section id = openModal2>
        <h2>Cahier des charges</h2>
        <img src="../assets/img/cahier-des-charges.png" alt="Cahier des charges" title="Cahier des charges">
    </section>
</button>

<button>
    <section id = openModal3>
        <h2>Travail avec JavaScript</h2>
        <img src="../assets/img/js.png" alt="Dynamiser un espace commentaire" title="Dynamiser un espace commentaire">
    </section>
</button>

<button>
    <section id = openModal4>
        <h2>Mon site de tests</h2>
        <img src="../assets/img/logo.jpg" alt="Mon site de tests" title="Mon site de tests">
    </section>
</button>
</div>

</template>

<style scoped>
div{
    margin-top:100px ;
    margin-bottom: 100px;
    display: flex;
}
button{
    background-color: #ffff;
    border:none;
}

section{
    height: 350px;
    display: flex;
    flex-direction: column;
}
section:hover{
    border-right: solid #33402B;
    border-bottom: solid #33402B;
    box-shadow: 0.5rem 0.5rem 0.5rem  #33402B;
}
section:active{
    border-right: solid #618C6C;
    border-bottom: solid #618C6C;
    box-shadow: 0.5rem 0.5rem 0.5rem  #618C6C;
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

