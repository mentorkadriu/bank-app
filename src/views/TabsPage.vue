<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">
        <ion-tab-button tab="tab1" href="/tabs/tab1" router-direction="forward">
          <vue-feather type="credit-card" size="24"></vue-feather>
          <ion-label>Dashboard</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab2" href="/tabs/tab2">
          <vue-feather type="dollar-sign"></vue-feather>
          <ion-label>Spendings</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab3" href="/tabs/tab3">
          <vue-feather type="message-square"></vue-feather>
          <ion-label>Messages</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonTabBar, IonTabButton, IonTabs, IonPage, IonRouterOutlet, IonLabel } from '@ionic/vue';

export default defineComponent({
  name: 'TabsPage',
  components: { IonTabs, IonTabBar, IonTabButton, IonPage, IonRouterOutlet, IonLabel },
});
</script>
