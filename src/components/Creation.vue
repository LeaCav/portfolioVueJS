<script setup>
import { ref } from 'vue'; //importer la fonction 'ref' de la bibliothèque Vue. Utilisée pour créer une référence réactive à une valeur.
import Modal from './modals/Modal.vue'; //j'importe mon component Modal afin de le lier à mon component Creation

//Je crée une constante contenant un tableau répertoriant les données de chaque création
const creations = ref ([
    {
        title: 'Mon Curriculum Vitae',
        image: '../src/assets/img/cv1.png',
        img: '../src/assets/img/cv2.png',
        date: '30/01/2024',
        usedTech: 'HTML5 / CSS3',
        link: 'https://github.com/LeaCav/cv-lea-cavalli.git'
    },
    {
        title: 'Cahier des charges',
        image: '../src/assets/img/cahier-des-charges.png',
        img: '../src/assets/img/cahier-des-charges2.png',
        date: '15/02/2024',
        usedTech: 'Google doc / Inkscape / Paint 3D / Adobe color',
        link: '../src/assets/cahier-des-charges-léa-cavalli.html',
    },
    {
        title: 'Travail avec JavaScript' ,
        image: '../src/assets/img/js.png',
        img: '../src/assets/img/js.png',
        date: '26/02/2024',
        usedTech: 'HTML 5 / CSS 3 / JavaScript',
        link: 'https://github.com/LeaCav/dynamiser-un-espace-commentaire.git' ,
    },
    {
        title: 'Mon site de tests',
        image: '../src/assets/img/logo.png',
        img: '../src/assets/img/mon-site2.png',
        date: '27/02/2024',
        usedTech: 'HTML 5 / CSS 3 / JavaScript / Inkscape / Adobe color',
        link: 'https://github.com/LeaCav/mon-site-de-tests.git',
    },
]);

// je crée une constante dont la référence cible le contenu des {}
const selectedProject = ref({});

// je crée une constante dont la référence est "false"
const isModalOpened = ref(false);

// je crée une constante openModal réactive à un évènement
const openModal = (e) => {
    selectedProject.value = creations.value[Number(e.target.id)]; //ici la valeur va cibler l'id dans le target
    isModalOpened.value = true; //dans ce cas isModalOpen prends la valeur "true"
};

const closeModal = () => {
    isModalOpened.value = false;
};
</script>

<template>
    <h2>Mes projets</h2>
    <div id="myCreations">
        <section v-for="(creation, index) in creations">
            <h3>{{ creation.title }}</h3>
            <button @click="openModal">
                <img :src="creation.image" :id="index" :alt="'${creation.image}'">
            </button>
            <Modal :currentProject="selectedProject" :isOpen="isModalOpened" @modal-close="closeModal" name="first-modal">
                <template #header>
                </template>
                <template #content>
                </template>
                <template #footer>
                </template>
            </Modal>
        </section>
    </div> 
</template>

<style scoped>
h2{
    Margin-top: 100px;
    width: 400px;
    color: #F2C46D;
    font-size: 1.4rem;
    background: rgb(51,64,43);
    background: radial-gradient(circle, rgba(51,64,43,1) 0%, rgba(255,255,255,1) 100%);
}
#myCreations{
    margin-top:30px ;
    margin-bottom: 100px;
    display: flex;
}
section{
    height: 350px;
    display: flex;
    flex-direction: column;
}
button{
    height: 350px;
    background-color: #ffff;
    border:none;
}
button:hover{
    box-shadow: 0.5rem 0.5rem 0.5rem  #33402B;
}
button:active{
    box-shadow: 0.5rem 0.5rem 0.5rem  #618C6C;
}
h3{
    font-size: 1.2rem;
}
img{
    width: 300px;
    height: 300px;
    margin: 10px;
    cursor:pointer;
}
</style>

