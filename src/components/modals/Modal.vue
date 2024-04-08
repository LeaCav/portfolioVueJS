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
                <div class="modal-header">
                    <slot name="header">
                        <h2> {{ currentProject.title }} </h2>
                    </slot>
                </div>
                <div class="modal-body">
                    <slot name="body">
                        <img :src="currentProject.img" :alt="'${currentProject.img}'" class="imgProject">
                        <p>Date de création : {{ currentProject.date }}</p>
                        <p>Technologies utilisées : {{ currentProject.usedTech }}</p>
                    </slot>
                </div>
                <div class="modal-footer">
                    <slot name="footer">
                        <a :href="currentProject.link" target="_blank">Lien vers ce projet</a>
                    </slot>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
*{
    background-color: white;
}
.modal-mask{
    margin: 0 0 0 400px;
    padding: 50px;
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: auto;
    background-color: rgba(0, 0, 0, 0.3);
}
.modal-wrapper{
    width: auto;
}
.modal-container{
    margin:0;
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
.imgProject{
    margin: 2px;
    padding: 0;
    width: auto;
    height: 300px ;
}

</style>
