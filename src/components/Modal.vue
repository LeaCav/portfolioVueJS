<script>

export default {
    name:'Modal', 
    data(){
        return  {
            isVisible:false,
            modalData: {},
        };
    },
    methods:{
       openModal(data){
            this.modalData = data;
            this.isVisible = true;
        },
        closeModal(){
            this.isVisible = false;
        },
    }
};
</script>
<template>
 
    <div class="modal" v-if="isVisible">
        <div class="button">
            <button @click="closeModal">
                <img src="../assets/img/icons8-fermer-la-fenêtre-100.png" alt="close">
            </button>
        </div>
        <h2>TEST</h2>
        <p>Date: TEST</p>
        <p>Used Technologies:TEST</p>
    </div>
</template>

<style scoped>
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
    z-index: 9999;
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

/* Your scoped styles here */
</style>
