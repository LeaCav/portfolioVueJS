<template>
    <figure id="presentation">
        <img src="../assets/img/photo-identité.png" alt="Léa Cavalli" title="Léa Cavalli">
    </figure>
    <strong>
        Je m'appelle Léa Cavalli, j'ai 33 ans et après 7 années passées dans le milieu de la petite enfance j'ai décidé de me 
        reconvertir dans le développement web et web mobile.
    </strong>
    <section>
        <h2>Mes compétences :</h2>
        <ul>
            <li>Visual Studio Code</li>
            <li>HTML5</li>
            <li>CSS3</li>
            <li>Lightroom</li>
            <li>Inkscape</li>
        </ul>
    </section>
    
</template>

<style scoped>
@font-face {
    font-family: "Relief";
    src: url(../assets/fonts.ReliefSingleLineOutline-Regular.woff2), url(../assets/fonts.ReliefSingleLineOutline-Regular.ttf);
}
figure{
    width: 200px;
    height: 200px;
    margin: 20px;
    align-self: center;
}
figure img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 50%;
    box-shadow: 0.8rem 0.5rem #33402b;
}
strong{
    font-family: "Relief";
}
section{
    margin-top: 20px ;
    display: flex;
    flex-direction: column;
    margin-left: 35rem;
    text-align: start;
}
</style>

<script setup>


</script>