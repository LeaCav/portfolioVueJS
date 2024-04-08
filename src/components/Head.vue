<script>
</script>

<template>
    <div>
        <a href="#" class="img">
            <img src="../assets/img/icons8-page-d’accueil-64.png" alt="home">
        </a>
    </div>
    
    <h1>Mon portfolio</h1>
    <strong>Léa Cavalli</strong>
    
    <nav>
        <ul>
            <li><a href="#presentation">Présentation</a></li>
            <li><a href="#myCreations">Mes projets</a></li>
            <li><a href="#contactMe">Me contacter</a></li>
            <li><a href="../views/Error.vue">Error 404</a></li>
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
div, .img{
    padding: 0;
    text-align: start;
}
img{
    width: 100px;
    margin: 10px;
    padding: 10px;
    position: fixed;
    border-radius: 50%;
}
img:hover{
    background-color: #F2C46D;
}
img:active{
    opacity:0.3;
}
h1{
    font-family: "Giorgio";
    font-size: 50px;
    margin-bottom: 10px;
    padding: 0;
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