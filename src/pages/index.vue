<template>
  <v-app :style="{ background: $vuetify.theme.themes.light.colors.primary }">
    <!-- ***** START COMPONENT => SIDEBAR ***** -->
    <Sidebar />
    <!-- ***** END COMPONENT => SIDEBAR ***** -->
    <v-main>
      <v-container class="px-6 mt-n2">
        <!-- ============ info cards ============ -->
        <v-row>
          <v-col v-for="(item, index) in cardInfo" cols="12" sm="4">
            <v-card :color="item.color" theme="dark" class="rounded-xl" height="150">
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title class="text-h5 mt-10">{{ item.title }}</v-card-title>
                  <v-card-subtitle>{{ item.flights }}</v-card-subtitle>
                </div>
                <v-img :src="item.avatar" class="mr-4 mt-5 absolute"></v-img>
              </div>
            </v-card>
          </v-col>
        </v-row>
        <!-- ============ chartjs ============ -->
        <v-row>
          <!--  -->
          <v-col cols="12" sm="4">
            <v-card class="mx-auto bg-white" height="400px">
              <v-card-item title="Top Airlines">
                <!-- ***** START COMPONENT => DOUGHNUT ***** -->
                <Doughnut />
                <!-- ***** END COMPONENT => DOUGHNUT ***** -->
                <span class="d-flex justify-center mt-5">
                  <v-btn @click="exportGraphic()">
                    Export Graphic
                  </v-btn>
                </span>
              </v-card-item>
            </v-card>
          </v-col>
          <v-col cols="12" sm="8">
            <v-card class="mx-auto bg-white" height="400px">
              <v-card-item title="Airlines flights">
                <v-tabs v-model="selectedTab" align-tabs="center" class="mb-2">
                  <v-tab value="two">Bar Graphic</v-tab>
                  <v-tab value="one">Bubble Graphic</v-tab>
                  <v-tab value="three">Line Graphic</v-tab>
                </v-tabs>
                <v-window v-model="selectedTab">
                  <v-window-item value="one">
                    <!-- ***** START COMPONENT => BUBBLE ***** -->
                    <Bubble />
                    <!-- ***** END COMPONENT => BUBBLE ***** -->
                  </v-window-item>
                  <v-window-item value="two">
                    <!-- ***** START COMPONENT => BAR ***** -->
                    <Bar />
                    <!-- ***** END COMPONENT => BAR ***** -->
                  </v-window-item>
                  <v-window-item value="three">
                    <!-- ***** START COMPONENT => BAR ***** -->
                    <Line />
                    <!-- ***** END COMPONENT => BAR ***** -->
                  </v-window-item>
                </v-window>
              </v-card-item>
            </v-card>
          </v-col>
        </v-row>
        <!-- ============ frecuent travelers ============ -->
        <v-row>
          <v-col cols="12" sm="12">
            <v-card class="mx-auto bg-white">
              <v-card-item title="Top Frequent Travelers">
                <template v-slot:subtitle>Overview of latest month</template>
              </v-card-item>
              <v-card-text>
                <v-row align="center" no-gutters>
                  <v-col cols="12">
                    <v-sheet class="mx-auto bg-white w-100" max-width="700">
                      <v-slide-group show-arrows>
                        <v-slide-group-item v-for="(item, index) in topTravelers" :key="index"
                          v-slot="{ isSelected, toggle }">
                          <v-btn :color="isSelected ? 'success' : undefined" class="ma-2" rounded @click="toggle">
                            @{{ item.name }}
                          </v-btn>
                        </v-slide-group-item>
                      </v-slide-group>
                    </v-sheet>
                  </v-col>
                </v-row>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
//
import Sidebar from "@/components/Sidebar.vue"
import Doughnut from "@/components/Doughnut.vue"
import Bubble from "@/components/Bubble.vue"
import Bar from "@/components/Bar.vue"
import Line from "@/components/Line.vue"

const cardInfo = [
  { color: "#FFC800", title: "Boeing", flights: "100 Flights", avatar: "https://raw.githubusercontent.com/zakaria-29-dev/vuejs-vuetify-flight-dashboard-chartjs-vuechartjs/main/public/av.png" },
  { color: "#FFC800", title: "Airbus", flights: "150 Flights", avatar: "https://raw.githubusercontent.com/zakaria-29-dev/vuejs-vuetify-flight-dashboard-chartjs-vuechartjs/main/public/av.png" },
  { color: "#001C67", title: "Total Flights", flights: "250", avatar: "https://raw.githubusercontent.com/zakaria-29-dev/vuejs-vuetify-flight-dashboard-chartjs-vuechartjs/main/public/map.png" }
];
</script>

<script>
export default {
  data: () => ({
    topTravelers: [
      { name: "Angela" },
      { name: "Jana" },
      { name: "Leifer" },
      { name: "Alex" },
      { name: "Fernando" },
      { name: "Samuel" },
      { name: "Jesus" },
      { name: "Cristian" },
      { name: "Angie" },
      { name: "Karen" },
    ],
    selectedTab: null
  }),
  components: {
    Sidebar,
    Doughnut,
    Bubble,
    Bar,
    Line
  },
  methods: () => {
    this.greet()
  }
}

function exportGraphic() {
  alert("Something goes wrong, try it again.")
}
</script>