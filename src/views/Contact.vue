<template>
  <div>
    <v-container fluid class="grey lighten-1">
      <v-row dense>
        <v-col cols="3">
          <v-card class="pa-1" outlined> status</v-card>
        </v-col>

        <v-col cols="6">
          <!-- <v-card class="pa-2" outlined> cam</v-card> -->
          <v-card>
            <v-tabs
              v-model="tab"
              background-color="light-blue"
              dark
              centered
              center-active
              class="pa-1"
              outlined
            >
              <v-tabs-slider color="yellow"></v-tabs-slider>
              <v-tab v-for="item in items" :key="item.tab">
                {{ item.tab }}
              </v-tab>
            </v-tabs>

            <v-tabs-items v-model="tab">
              <v-tab-item>
                <v-container>
                  <!-- <v-col> -->
                  <v-card height="480px" width="720px" class="grey lighten-2">
                    <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                    <v-card-text>{{ "All Tab" }}</v-card-text>
                  </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>

              <v-tab-item>
                <v-container>
                  <!-- <v-col> -->
                  <v-card height="480px" width="720px" class="grey lighten-2">
                    <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                    <v-card-text>{{ "Camera1 Tab" }}</v-card-text>
                  </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>

              <v-tab-item>
                <v-container>
                  <!-- <v-col> -->
                  <v-card height="480px" width="720px" class="grey lighten-2">
                    <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                    <v-card-text>{{ "Camera2 Tab" }}</v-card-text>
                  </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>

              <v-tab-item>
                <v-container>
                  <!-- <v-col> -->
                  <v-card height="480px" width="720px" class="grey lighten-2">
                    <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                    <v-card-text>{{ "PTZ Tab" }}</v-card-text>
                  </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>

              <v-tab-item>
                <v-container>
                  <!-- <v-col> -->
                  <v-card height="480px" width="720px" class="grey lighten-2">
                    <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                    <v-card-text>{{ "Map Tab" }}</v-card-text>
                  </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>
            </v-tabs-items>
          </v-card>
        </v-col>
        <v-col cols="3">
          <v-card class="pa-1" >
            <v-row dense>
              <v-card height="200px" width="350px" class="purple lighten-3" outlined>
                <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                <v-card-text>{{ "Joy Software:" }}</v-card-text>

                <v-row align="center">
                  <v-col class="d-flex" cols="12" sm="12">
                    <v-select 
                      :items="speedItems" 
                      label="Select Speed" 
                      outlined 
                      dense   
                    >       
                    </v-select>
                  </v-col>
                </v-row>

                <v-row align="center" no-gutters >
                  
                  <v-col class="d-flex justify-center" cols="4"><v-btn small>FW</v-btn></v-col>
                  <v-col class="d-flex justify-center" cols="4">
                    <v-btn small>FW</v-btn>
                  </v-col>
                  <v-col class="d-flex justify-center" cols="4"><v-btn small>FW</v-btn></v-col>
                  
                </v-row>
                <v-row align="center"></v-row>
                <v-row align="center"></v-row>

              </v-card>
            </v-row>

            <v-row dense>
              <v-card
                height="200px"
                width="350px"
                outlined
                class="purple lighten-2"
              >
                <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                <v-card-text>{{ "PTZ Camera:" }}</v-card-text>
              </v-card>
            </v-row>

            <v-row dense>
              <v-card height="200px" width="350px" class="purple lighten-1">
                <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                <v-card-text>{{ "IO Control:" }}</v-card-text>
              </v-card>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  export default {
    data: () => ({
      myitems: ['Foo', 'Bar', 'Fizz', 'Buzz'],
    }),
  }
</script>