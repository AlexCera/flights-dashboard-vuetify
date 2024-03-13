<template>
    <v-navigation-drawer v-model="drawer" color="#20BF55" class="rounded-e-xl">
        <!--  -->
        <v-sheet color="#20BF55" class="pa-4 rounded-e-xl text-center">
            <v-progress-circular model-value="80" color="#001C67" :size="100" :width="2">
                <v-avatar size="85">
                    <v-img src="https://randomuser.me/api/portraits/men/18.jpg"></v-img>
                </v-avatar>
            </v-progress-circular>
            <div class="mt-4">Jhon Doe</div>
            <span class="mb-6 text-caption">jhon.doe@mail.co</span>
        </v-sheet>
        <!--  -->
        <v-list>
            <v-list-item v-for="(item, index) in pages" :key="index" :value="item" active-class="border"
                :ripple="false">
                <template v-slot:prepend>
                    <v-icon :icon="item.icon" color="#B449239"></v-icon>
                </template>
                <v-list-item-title v-text="item.name" class="text-capitalize"></v-list-item-title>
            </v-list-item>
        </v-list>
        <!--  -->
        <h5 class="ml-5 text-subtitle-1 text-black">Active Users</h5>
        <v-row align="center" class="spacer ml-16 mt-4" no-gutters>
            <v-col v-for="(item, index) in activeUsers" cols="4" sm="2" md="1">
                <v-avatar size="36px">
                    <v-img alt="Avatar" :src="item.avatar" :title="item.name"></v-img>
                </v-avatar>
            </v-col>
            <v-col cols="4" sm="2" md="1">
                <v-avatar size="36px" color="#B49239">+10</v-avatar>
            </v-col>
        </v-row>
        <!--  -->
        <div style="position: relative;z-index: 9999;" class="mt-2 w-100">
            <v-img src="https://raw.githubusercontent.com/zakaria-29-dev/vuejs-vuetify-flight-dashboard-chartjs-vuechartjs/main/public/map.png" contain max-height="100"></v-img>
        </div>
    </v-navigation-drawer>
</template>

<script setup>
import { ref } from "vue";
const pages = [
    { name: "Dashborad", icon: "mdi mdi-home-outline" },
    { name: "Flights", icon: "mdi mdi-airplane" },
    { name: "Reports", icon: "mdi mdi-file-chart-outline" },
    { name: "Statistics", icon: "mdi mdi-chart-pie" },
    { name: "Settings", icon: "mdi mdi-cog-outline" },
];

const activeUsers = [
    { name: "Andy", avatar: "https://randomuser.me/api/portraits/men/18.jpg" },
    { name: "Leyla", avatar: "https://randomuser.me/api/portraits/women/3.jpg" },
    { name: "Meli", avatar: "https://randomuser.me/api/portraits/women/11.jpg" },
    { name: "Smith", avatar: "https://randomuser.me/api/portraits/men/14.jpg" },
];
const drawer = ref(null);
</script>

<script>
export default {
    data: () => ({
        cards: ["Today", "Yesterday"],
        drawer: null,
    })
}
</script>

<style>

</style>