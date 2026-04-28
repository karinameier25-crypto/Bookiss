<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Bookiss</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
        <ion-button @click="$router.push('/home')">HOME</ion-button>
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">BOOKISS</ion-title>
        </ion-toolbar>
      </ion-header>

        <div id="container" v-if="livro">
  <img :src="livro.img" style="width:200px; border-radius:10px;" />

  <h1>{{ livro.nome }}</h1>
  <p><strong>Autor:</strong> {{ livro.autor }}</p>
  <p>{{ livro.descricao }}</p>
</div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">

import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton } from '@ionic/vue';
import { useRoute } from 'vue-router';
import { ref, watch } from 'vue';

const route = useRoute();
const id = route.params.id;

console.log(id);

const livros = [
  {
    id: '1',
    nome: "Ao Haru Ride",
    autor: "Io Sakisaka",
    descricao: "Ao Haru Ride é um romance shōjo que acompanha Futaba Yoshioka, que reencontra seu primeiro amor, Kou Tanaka (Mabuchi), no ensino médio. Kou mudou, tornando-se frio após traumas familiares, forçando Futaba a lidar com a diferença entre o passado e o presente. A história foca no amadurecimento, superação de traumas e redescoberta do amor. ",
    img: "https://m.media-amazon.com/images/I/81oW5KEVNyL.jpg"
  },
  {
    id: '2',
    nome: "Kimi ni Todoke",
    autor: "Karuho Shiina",
    descricao: "Kimi ni Todoke é um romance escolar sobre Sawako Kuronuma, uma garota tímida apelidada de Sadako devido à sua aparência sombria, que a faz ser excluída. Sua vida muda quando Shouta Kazehaya, o garoto mais popular e gentil da sala, aproxima-se dela, ajudando-a a fazer amigos e a superar obstáculos, cultivando um doce romance.",
    img: "https://m.media-amazon.com/images/I/715Jg0kQBgL._UF1000,1000_QL80_.jpg"
  },
  {
    id: '3',
    nome: "Horimiya",
    autor: "HERO",
    descricao: "Romance com lados ocultos",
    img: "https://m.media-amazon.com/images/I/71hsNIpmdZL.jpg"
  }
];

const livro = ref<any>(null);

watch(
  () => route.params.id,
  (novoId) => {
    livro.value = livros.find(l => l.id === novoId);
  },
  { immediate: true }
);
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
