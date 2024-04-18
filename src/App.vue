<script setup>
import { ref } from 'vue';
import Modal from './components/Modal.vue';

const showModal = ref(false);

function modalShow() {
    showModal.value = true;
}
function modalClose() {
    showModal.value = false;
}
</script>

<template>
    <main>
        <header>
            <div class="header-title">
                Sekii&trade; - VueJS Modal Component
            </div>
        </header>
        <section>
            <button class="modal-show-button" @click="modalShow()">
                Show Modal
            </button>
        </section>
    </main>

    <Modal v-if="showModal" @close="modalClose()" />
</template>

<style scoped>
    main {
        height: 100vh;
        display: flex;
        flex-direction: column;
    }

    main header {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    main section {
        flex: 2;
        display: flex;
        justify-content: center;
        align-items: flex-start;
    }

    .header-title {
        /* background-color: aliceblue; */
        text-align: center;

        font-size: 48pt;
        line-height: 78px;
    }
    .modal-show-button {
        margin-top: 20px;
        padding: 15px 30px;
        cursor: pointer;
        font-size: 14pt;
    }

</style>
