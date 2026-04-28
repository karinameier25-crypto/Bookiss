<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Bookiss
        </ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-button v-if="!logado" @click="$router.push('/login')">LOGIN</ion-button>
      <ion-button v-if="!logado" @click="$router.push('/cadastro')">CADASTRO</ion-button>
      <h2 v-if="logado">Bem-vindo(a)!</h2>
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">BOOKISS</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
     <h1>Bookiss</h1>
     <p>Aqui você encontra os melhores livros de romance!</p>
      </div>

     <div id="cards">

  <ion-card>
    <ion-img src="https://m.media-amazon.com/images/I/81oW5KEVNyL.jpg"></ion-img>
    <ion-card-header>
      <ion-card-title>Ao Haru Ride</ion-card-title>
      <ion-card-subtitle>Io Sakisaka</ion-card-subtitle>
    </ion-card-header>
    <ion-button @click="$router.push('/detalhes/1')">VER DETALHES</ion-button>
  </ion-card>

  <ion-card>
    <ion-img src="https://m.media-amazon.com/images/I/715Jg0kQBgL._UF1000,1000_QL80_.jpg"></ion-img>
    <ion-card-header>
      <ion-card-title>Kimi ni Todoke</ion-card-title>
      <ion-card-subtitle>Karuho Shiina</ion-card-subtitle>
    </ion-card-header>
    <ion-button @click="$router.push('/detalhes/2')">VER DETALHES</ion-button>
  </ion-card>

  <ion-card>
    <ion-img src="https://m.media-amazon.com/images/I/71hsNIpmdZL.jpg"></ion-img>
    <ion-card-header>
      <ion-card-title>Horimiya</ion-card-title>
      <ion-card-subtitle>HERO</ion-card-subtitle>
    </ion-card-header>
    <ion-button @click="$router.push('/detalhes/3')">VER DETALHES</ion-button>
  </ion-card>

</div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton, IonImg, IonCardTitle, IonCardSubtitle, IonCardHeader, IonCard } from '@ionic/vue';
import { ref, onMounted } from 'vue';

const logado = ref(false);

onMounted(() => {
  if (localStorage.getItem('logado') === 'true') {
    logado.value = true;
  }
});
</script>

<style scoped>#container {
  text-align: center;
  margin-top: 20px;
}
#container {
  text-align: center;
  margin-top: 20px;
}

#container h1 {
  font-size: 32px;
  margin-bottom: 5px;
}

#container p {
  color: #aaa;
  margin: 0;
}

/* 🔥 UM container só pros cards */
#cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  max-width: 900px;
  margin: 30px auto;
}

/* ajusta os cards */
ion-card {
  text-align: center;
}

ion-img {
  height: 250px;
  object-fit: cover;
}
</style>