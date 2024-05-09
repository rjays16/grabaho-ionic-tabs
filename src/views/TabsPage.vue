<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">
        <ion-tab-button tab="tab1" href="/tabs/tab1" @click="updateActiveTab('tab1')">
          <img :src="isActive('tab1') ? activeHomeImage : homeImage" alt="Tab 1 Icon" />
          <ion-label style="margin-top: 5px;" :class="{ 'active-tab-label': isActive('tab1') }">Home</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab2" href="/tabs/tab2" @click="updateActiveTab('tab2')">
          <img :src="isActive('tab2') ? activeBookingImage : bookingImage" alt="Tab 2 Icon" />
          <ion-label style="margin-top: 5px;" :class="{ 'active-tab-label': isActive('tab2') }">Bookings</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab3" href="/tabs/tab3" @click="updateActiveTab('tab3')">
          <img :src="isActive('tab3') ? activeCreditsImage : creditImage" alt="Tab 3 Icon" />
          <ion-label style="margin-top: 5px;" :class="{ 'active-tab-label': isActive('tab3') }">Credits</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab4" href="/tabs/tab4" @click="updateActiveTab('tab4')">
          <img :src="isActive('tab4') ? activeProfileImage : profileImage" alt="Tab 4 Icon" />
          <ion-label style="margin-top: 5px;" :class="{ 'active-tab-label': isActive('tab4') }">Profile</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script setup lang="ts">
import { IonTabBar, IonTabButton, IonTabs, IonLabel, IonIcon, IonPage, IonRouterOutlet } from '@ionic/vue';
import { ellipse, square, triangle } from 'ionicons/icons';
import { ref } from 'vue';

const activeTab1 = ref<string>('tab1');
const activeTab2 = ref<string>('tab2');
const activeTab3 = ref<string>('tab3');
const activeTab4 = ref<string>('tab4');

function isActive(tab: string): boolean {
  return activeTab1.value === tab;
}

const activeHomeImage =  '/menu/active_home.png';
const homeImage =  '/menu/home.png';

const activeBookingImage =  '/menu/active_bookings.png';
const bookingImage =  '/menu/bookings.png';

const activeCreditsImage =  '/menu/active_credits.png';
const creditImage =  '/menu/credits.png';

const activeProfileImage =  '/menu/active_profile.png';
const profileImage =  '/menu/profile.png';

function updateActiveTab(tab: string) {
  activeTab1.value = tab;
  activeTab2.value = tab;
  activeTab3.value = tab;
  activeTab4.value = tab;
}
</script>

<style scoped>
.active-tab-label {
  color: #FFA53C;
}
</style>
