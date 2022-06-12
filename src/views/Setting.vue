<template>
  <nav>
      <h1>This is a setting page</h1>
      <div>
    <v-container fluid class="grey lighten-1">
      <v-row dense >
        <v-col
          cols="8"
          class="pa-2 fill-height d-flex flex-column justify-center align-center"
        >
          <v-card>
            <v-tabs
              v-model="tab"
              background-color="light-blue"
              dark
              centered
              center-active
            
            >
              <v-tabs-slider color="yellow"></v-tabs-slider>
              <v-tab v-for="item in items" :key="item.tab">
                {{ item.tab }}
              </v-tab>
            </v-tabs>

            <v-tabs-items v-model="tab">
              <v-tab-item>
                <v-container >
                  <!-- <v-col> -->
                    <v-card height="480px" width="720px" class="grey lighten-2">
                      <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                      <v-card-text>{{ "All Tab" }}</v-card-text>
                    </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>

              <v-tab-item>
                <v-container >
                  <!-- <v-col> -->
                    <v-card height="480px" width="720px" class="grey lighten-2">
                      <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                      <v-card-text>{{ "Camera1 Tab" }}</v-card-text>
                    </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>

              <v-tab-item>
                <v-container >
                  <!-- <v-col> -->
                    <v-card height="480px" width="720px" class="grey lighten-2">
                      <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                      <v-card-text>{{ "Camera2 Tab" }}</v-card-text>
                    </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>

              <v-tab-item>
                <v-container >
                  <!-- <v-col> -->
                    <v-card height="480px" width="720px" class="grey lighten-2">
                      <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                      <v-card-text>{{ "PTZ Tab" }}</v-card-text>
                    </v-card>
                  <!-- </v-col> -->
                </v-container>
              </v-tab-item>

              <v-tab-item>
                <v-container >
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

        <v-col
          cols="4"
          class="pa-2 fill-height d-flex flex-column justify-center align-center"
        >
          <v-row dense>
            <v-card height="200px"  width="350px" class="grey lighten-2">
              <!-- <v-card-text>{{ item.content }}</v-card-text> -->
              <v-card-text>{{ "Map Tab" }}</v-card-text>
            </v-card>
          </v-row>

          <br>

          <v-row dense>
            <v-card height="200px"  width="350px" class="grey lighten-2">
              <!-- <v-card-text>{{ item.content }}</v-card-text> -->
              <v-card-text>{{ "Map Tab" }}</v-card-text>
            </v-card>
          </v-row>

        </v-col>
      </v-row>
    </v-container>
  </div>
  </nav>

  
</template>

<script>
export default {

}
</script>

<style>

</style>