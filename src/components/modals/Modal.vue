<script setup>
import { ref } from 'vue' //importer la fonction 'ref' de la bibliothèque Vue. Utilisée pour créer une référence réactive à une valeur.
import { onClickOutside } from '@vueuse/core' //importe la fonction depuis la bibliothèque VueUse. Permet de détecter les clics en dehors d'un élément spécifique.

const props = defineProps ({ //variable permettant de définir que les propriétés qu'un composant peut recevoir de son parent sont de
    isOpen : Boolean, //type booléen (true/false)
    currentProject: Object,
});

//je crée une constante permettant de définir qu'un composant peut émettre l'évènement "modal-close"
const emit = defineEmits (['modal-close']);

//je crée une constante réactive dont la référence est "null"
const target = ref(null);

//j'indique à ma fonction onClickOutside que lorsque je clique en dehors de ma div "ref=target", j'émet l'évènement 'close-modal'
onClickOutside(target, () => emit('modal-close'))
</script>

<template>
    <div v-if="isOpen" class="modal-mask">
        <div class="modal-wrapper">
            <div class="modalContainer" ref="target">
                <div class="button">
                    <button @click="closeModal">
                        <img src="../../assets/img/icons8-fermer-la-fenêtre-100.png" alt="close">
                    </button>
                </div>
                </div class="modal-header">
                    <slot name="header"> {{ currentProject.title }} </slot>
                </div>
                <div class="modal-body">
                    <slot name="content">
                        <img :src = "'${currentProject.img}'" :alt="'${currentProject.img}'">
                        <p>Date de création : {{ currentProject.date }}</p>
                        <p>Technologies utilisées : {{ currentProject.usedTech }}</p>
                    </slot>
                </div>
                <div class="modal-footer">
                    <slot name="footer">
                        <a :href="''" target="_blank">Lien vers le projet</a>
                    </slot>
                </div>
            </div>
</template>

<style scoped>
*{
    background-color: white;
}
.modal-mask{
    margin: 30px 0 0 250px;
    padding: 35px;
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 1000px;
    height: 600px;
    background-color: rgba(0, 0, 0, 0.3);
}
.modal-wrapper{
    width: 800px;
    height: 400px;
}
.modal-container{
    text-align: center;
}
.button{
    text-align: end;
}
button{
    width: 80px;
    height: 80px;
    padding: 0;
    background-color: white;
    border: none;
}
img{
    width: 100%;
    margin:0;
    padding: 0;
}
img:active{
    opacity:0.3;
}
.modal-header{
    width: 800px;
}
.modal-body{
    width: 800px;
}
.modal-footer{
    width: 800px;
}
</style>
