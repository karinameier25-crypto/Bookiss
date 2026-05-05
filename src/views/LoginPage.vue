<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Bookiss</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">BOOKISS</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
        <ion-card>
            <ion-card-header>
                <ion-card-title>Login</ion-card-title>
            </ion-card-header>
            <ion-card-content>
                <h2>E-mail:</h2>
                <ion-input v-model="email" type="text" placeholder="Digite seu E-mail"></ion-input>
                <h2>Senha:</h2>
                <ion-input v-model="senha" type="password" placeholder="Digite sua senha"></ion-input>
                <ion-button v-if="email && senha" @click="$router.push('/home')">Entrar</ion-button>
            </ion-card-content>
        </ion-card>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton,  IonCard, IonCardHeader, IonCardTitle, IonCardContent, IonInput  } from '@ionic/vue';
import { ref } from 'vue';

const email = ref('')
const senha = ref('')
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
