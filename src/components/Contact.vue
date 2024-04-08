<script setup>
let myRegex = /^[a-zA-Z-\s]+$/;
import { EMAIL } from '@/config.js';

// je crée une fonction en if/else afin de valider mon formulaire
function validateForm() {
    var identity = document.forms["contact"]["identity"];
    var objet = document.forms["contact"]["objet"];
    var message = document.forms["contact"]["message"];

// identity doit être rempli avec une valeur valide, comprenant des lettres et éventuellement des tirets sinon un message d'erreur apparait
    if (identity.value == "") {
        document.getElementById('errorName').innerHTML="Veuillez renseigner vos Nom et Prénom";
        errorName.style.color = 'red';
        return false;
    } else if(myRegex.test(identity.value) == false) {
        document.getElementById('errorName').innerHTML="Le champ doit comporter des lettres et des tirets uniquement";
        errorName.style.color = 'red';
        identity.value = "";
        return false;
    } else {
        document.getElementById('errorName').innerHTML=""
    }
// objet doit être rempli sinon un message d'erreur apparait
    if (objet.value == ""){
        document.getElementById('errorObjet').innerHTML="Veuillez entrer un objet";
        errorObjet.style.color = 'red';
        return false;
    } else {
        document.getElementById('errorObjet').innerHTML=""
    }
// message doit être rempli sinon un message d'erreur apparait
    if (message.value == ""){
        document.getElementById('errorMessage').innerHTML="Veuillez entrer un message";
        errorMessage.style.color = 'red';
        return false;
    } else {
        document.getElementById('errorMessage').innerHTML=""
    }
    return true;
    }

// je crée une fonction validant l'envoie si la fonction validateForm est true. Une message de validation apparait à la fin de l'envoie
function submit() {
    if (validateForm() == false) {
        contact.onsubmit = 'none';
    } else {
        document.getElementById('send').innerHTML="Votre message a bien été envoyé";
        send.style.color = '#618C6C';
        //je cible l'e-mail définie en variable d'environnement importé dans 'config.js'
        window.location.href =  "mailto:"+EMAIL+"?subject=["+identity.value+"] - "+objet.value+ "&body="+message.value;
        // je réinitialise les valeurs à zéro
        identity.value = "";
        objet.value = "";
        message.value = "";
    }
}
</script>

<template>
<div id="contactMe">
    <h2>Me contacter</h2>
    <form id="contact" ref="values" @submit.prevent="sendEmail" onsubmit="return validateForm()" method="post">
        <label for="indetity">Nom et Prénom</label>
        <input type="text" name="identity" id="identity" placeholder="Votre nom et prénom">
        <span class="error" id="errorName"></span>

        <label for="objet">Sujet</label>
        <input type="text" name="objet" id="objet" placeholder="L'objet de votre message">
        <span class="error" id="errorObjet"></span>

        <label for="message">Message</label>
        <textarea name="message" id="message" cols="30" rows="10" placeholder="Votre message"></textarea>
        <span class="error" id="errorMessage"></span>
        <span class="send" id="send"></span>
    </form>
    <button @click="submit"><img src="../assets/img/logo_telegram_airplane_air_plane_paper_airplane_icon_143169.png" alt="submit" title="envoyer"></button>
</div>

</template>

<style scoped>
div{
    width: 100%;
    margin: 0;
    background: rgb(242,179,102);
    background: linear-gradient(0deg, rgba(242,179,102,1) 0%, rgba(255,255,255,1) 100%);
    display: flex;
    flex-direction: column;
    align-items: end;
}
h2{
    font-size: 1.2rem;
}
form{
    width: 70%;
    display: flex;
    flex-direction: column;
}
label{
    text-align: start;
}
textarea, input{
    margin:5px 0;
    color:#618C6C;
    border: solid 1px #33402B;
}
#identity, #objet{
    width: 400px;
}
#errorName, #errorObjet{
    text-align: start;
}
button{
    width: 80px;
    margin: 10px 30px 30px;
    border:none;
    cursor: pointer;
    border-radius: 50%;
}
button:hover{
    box-shadow:0 0 0.5rem 0.5rem #618C6C;
}
button:active{
    box-shadow:0 0 0.5rem 0.5rem #33402B;
}

</style>

