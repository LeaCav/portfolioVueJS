<template>
<div>
    <h2>Me contacter</h2>
    <form>
        <textarea name="name" id="name" placeholder="Nom et Prénom"></textarea>
        <textarea name="message" id="message" cols="30" rows="10" placeholder="Votre message"></textarea>
    </form>
        <button><img src="../assets/img/logo_telegram_airplane_air_plane_paper_airplane_icon_143169.png" alt="send" title="envoyer"></button>
    
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
    display: flex;
    flex-direction: column;
}
textarea{
    margin:5px 0;
    color:#618C6C;
    border: solid 1px #33402B;
}
#name{
    width: 400px;
}
button{
    width: 80px;
    margin: 10px 30px;
    border:none;
    cursor: pointer;
    border-radius: 50%;
    
}
button:hover{
    box-shadow:0 0 0.5rem 0.5rem #618C6C;
}

</style>

<script setup>

</script>