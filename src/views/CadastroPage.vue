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

      <div id="container">
        <ion-card>
            <ion-card-header>
                <ion-card-title>Cadastre-se</ion-card-title>
            </ion-card-header>
            <ion-card-content>
                <h2>Nome:</h2>
                <ion-input type="text" placeholder="Digite seu nome"></ion-input>
                <h2>E-mail:</h2>
                <ion-input type="text" placeholder="Digite seu E-mail"></ion-input>
                <h2>Senha:</h2>
                <ion-input type="password" placeholder="Digite sua senha"></ion-input>
                <h2>Confirmar senha:</h2>
                <ion-input type="password" placeholder="Confirme sua senha"></ion-input>
                <ion-button>Cadastrar</ion-button>
            </ion-card-content>
        </ion-card>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton } from '@ionic/vue';
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
