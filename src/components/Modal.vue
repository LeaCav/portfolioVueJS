<template>
    <div class="modal">
        <h2>{{ modalData.title }}</h2>
        <img :src="modalData.img" alt="Project Image">
        <p>Date: {{ modalData.date }}</p>
        <p>Used Technologies: {{ modalData.usedTech }}</p>
        <a :href="modalData.link">Link</a>
    </div>
</template>

<script>
import { ref } from 'vue';

const modalData = ref({});

const open = (data) => {
    modalData.value = data;
};

const close = () => {
    modalData.value = {};
};

export default {
    setup() {
        return {
            open,
            close
        };
    }
};
</script>

<style scoped>
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
    z-index: 9999;
}

/* Your scoped styles here */
</style>
