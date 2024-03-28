<template>
        <div id="modal1">
            <img src="../assets/img/icons8-fermer-la-fenêtre-100.png" alt="close" class="close">
            <h2>Mon Curriculum Vitae</h2>
            <span>Créé le <time datetime="2024-01-30">30 janvier 2024</time></span>
            <h3>Technologies utilisées :</h3>
            <ul>
                <li>HTML 5</li>
                <li>CSS 3</li>
            </ul>
            <strong>Pour visiter cette page cliquez <a href ="https://github.com/LeaCav/cv-lea-cavalli/tree/main>ici</a></strong">ici</a></strong>
        </div>

        <div id="modal2">
            <img src="../assets/img/icons8-fermer-la-fenêtre-100.png" alt="close" class="close">
            <h2>Cahier des charges</h2>
            <span>Créé le <time datetime="2024-02-15">15 février 2024</time></span>
            <h3>Technologies utilisées :</h3>
            <ul>
                <li>Google doc</li>
                <li>Inkscape</li>
                <li>Paint 3D</li>
                <li>Adobe color</li>
            </ul>
            <strong>Pour visiter cette page cliquez <a href = "">ici</a></strong>
        </div>
    
        <div id="modal3">
            <img src="../assets/img/icons8-fermer-la-fenêtre-100.png" alt="close" class="close">
            <h2>Travail avec JavaScript</h2>
            <span>Créé le <time datetime=""></time></span>
            <h3>Technologies utilisées :</h3>
            <ul>
                <li>HTML 5</li>
                <li>CSS 3</li>
                <li>JavaScript</li>
            </ul>
            <strong>Pour visiter cette page cliquez <a href ="https://github.com/LeaCav/dynamiser-un-espace-commentaire">ici</a></strong>
        </div>

        <div id="modal4">
            <img src="../assets/img/icons8-fermer-la-fenêtre-100.png" alt="close" class="close">
            <h2>Mon site de tests</h2>
            <span>Créé le <time datetime=""></time></span>
            <h3>Technologies utilisées :</h3>
            <ul>
                <li>HTML 5</li>
                <li>CSS 3</li>
                <li>JavaScript</li>
                <li>Inkscape</li>
                <li>Adobe color</li>
            </ul>
            <strong>Pour visiter cette page cliquez <a href ="https://github.com/LeaCav/mon-site-de-tests">ici</a></strong>
        </div>

</template>

<style scoped>
div{
    background: rgb(255,255,255);
    background: linear-gradient(148deg, rgba(255,255,255,1) 0%, rgba(242,179,102,1) 100%);
}
img{
    width: 300px;
}
h2{
    font-size: 1.2rem;
}
</style>

<script setup>
import Creation from '@/components/Creation.vue'

    //get the modal
    var modal1 = document.getElementById("modal1");

//get the section that open the modal
var openModal1 = document.getElementById("openModal1");

//get the button that close the modal
var close = document.getElementByClassName("close");

//when the user clicks on the section, open the modal
openModal1.onclick = function() {
modal1.style.display = "block";
}

//when the user click on the button "close", close the modal
close.onclick = function() {
modal1.style.display = "none";
}

//when the user click anywhere outside of the modal, close import
window.onclick = function(event) {
if(event.target == modal){
    modal1.style.display = "none";
}
}
</script>