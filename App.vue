<template>
  <main>
    <button @click="btnPopupEmail = !btnPopupEmail">Botão Email</button>
    <button @click="btnPopup = !btnPopup">Botão Produto</button>
    <Modal :mostrar="btnPopupEmail">
      <template v-slot:cabecalho>
        <p class="">Email</p>
        <button @click="fecharPopup(btnPopupEmail)" class="button">x</button>
      </template>
      <template v-slot:corpo>
        <p class="">Senha</p>
      </template>
      <template v-slot:rodape>
        <button>Entrar</button>
      </template>
    </Modal>

    <Modal :mostrar="btnPopup">
      <template v-slot:cabecalho>
        <p class="">Não vá embora!</p>
        <button @click="fecharPopup(btnPopup)" class="button">x</button>
      </template>
      <template v-slot:corpo>
        <p class="">Compre mais</p>
      </template>
      <template v-slot:rodape>
        <p class="">produtos</p>
      </template>
    </Modal>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Modal from "./components/Modal.vue";

export default defineComponent({
  name: "App",
  components: {
    Modal
  },
  data () {
    return {
      btnPopupEmail: false,
      btnPopup: false
    }
  },
  methods: {
    fecharPopup(btn: boolean) {
      btn = !btn;
      console.log(btn);
      this.btnPopupEmail =  btn;
      this.btnPopup = btn;
    },
  }
});
</script>

<style>

</style>
