<script setup>
let myRegex = /^[a-zA-Z-\s]+$/;

function validateForm() {
    var identity = document.forms["contact"]["identity"];
    var objet = document.forms["contact"]["objet"];
    var message = document.forms["contact"]["message"];

    e.preventDefault();
    if (identity.value == "") {
        document.getElementById('errorObjet').innerHTML="Veuillez entrer un objet";
        errorName.style.color = 'red';
        identity.value = "";
        identity.focus();
        return false;
    } else if(myRegex.test(identity.value) == false) {
        document.getElementById('errorName').innerHTML="Le champ doit comporter des lettres et des tirets uniquement";
        errorName.style.color = 'red';
        identity.value = "";
    } else {
        document.getElementById('errorName').innerHTML=""
    }

    if (objet.value == ""){
        document.getElementById('errorObjet').innerHTML="Veuillez entrer un objet";
        errorObjet.style.color = 'red';
        objet.value = "";
        objet.focus();
        return false;
    } else {
        document.getElementById('errorObjet').innerHTML=""
    }

    if (message.value == ""){
        document.getElementById('errorMessage').innerHTML="Veuillez entrer un message";
        errorMessage.style.color = 'red';
        message.value = "";
        message.focus();
        return false;
    } else {
        document.getElementById('errorMessage').innerHTML=""
    }
    return true;
    }

function submit() {
    if (validateForm == false) {
        contact.onsubmit = 'none';
    } else {
        contact.onsubmit = true;
        document.getElementById('send').innerHTML="Votre message a bien été envoyé";
        send.style.color = '#618C6C';
    }
}
</script>

<template>
<div>
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
    <button type="submit"><img src="../assets/img/logo_telegram_airplane_air_plane_paper_airplane_icon_143169.png" alt="submit" title="envoyer"></button>
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

