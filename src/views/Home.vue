<template>
  <div>
    <v-container fluid class="grey lighten-1">
      <v-row dense>
        <v-col cols="3">
          <v-layout column align-center>
          <v-card>
            <v-tabs
              v-model="workTab"
              background-color="light-blue"
              dark
              centered
              class="pa-1"
              outlined
            >
              <v-tabs-slider color="yellow"></v-tabs-slider>
              <v-tab v-for="work in works" :key="work.tab">
                {{ work.tab }}
              </v-tab>
            </v-tabs>

            <v-tabs-items v-model="workTab">
              <!-- Working Details -->
              <v-tab-item>
                
                <v-container>
                  
                      <v-card
                    height="480px"
                    width="300px"
                    class="yellow lighten-3"
                    
                  >
                    <v-card-text class="text-subtitle-1 font-weight-bold">{{
                      "Project Details:"
                    }}</v-card-text>

                    <v-row dense>
                      <v-col cols="4" >
                          <v-subheader class="primary--text">Station Name:</v-subheader>
                      </v-col>
                      <v-col cols="8" class="px-5">
                        <v-text-field 
                          label="Name"
                          value="เขื่อนภูมิพล"  
                          readonly 
                                       
                        >
                        </v-text-field>
                      </v-col>                      
                    </v-row> 

                    <v-row dense>
                      <v-col cols="4">
                          <v-subheader class="primary--text">Unit Name:</v-subheader>
                      </v-col>
                      <v-col cols="8" class="px-5">
                        <v-text-field
                          label="Name"
                          value="เขื่อนภูมิพล-unit5"  
                          readonly                        
                        >
                        </v-text-field>
                      </v-col>                      
                    </v-row>

                    <v-row dense>
                      <v-col cols="4">
                          <v-subheader class="primary--text">Date:</v-subheader>
                      </v-col>
                      <v-col cols="8" class="px-5">
                        <v-text-field
                          label="Date"
                          value="24/10/2565"  
                          readonly                        
                        >
                        </v-text-field>
                      </v-col>                      
                    </v-row>

                    <v-row dense>
                      <v-col cols="4">
                          <v-subheader class="primary--text">Status:</v-subheader>
                      </v-col>
                      <v-col cols="8" class="px-5">
                        <v-text-field
                          label="Status"
                          value="Ongoing"  
                          readonly                        
                        >
                        </v-text-field>
                      </v-col>                      
                    </v-row>

                    
                  </v-card>
                  
                  
                </v-container>
              </v-tab-item>

              <!-- Project Status -->
              <v-tab-item>
                <v-container>
                  <v-card
                    height="480px"
                    width="300px"
                    class="yellow lighten-2"
                  >
                    <v-card-text class="text-subtitle-1 font-weight-bold">{{
                      "Project Status:"
                    }}</v-card-text>

              
                    <v-row dense>
                      <v-col cols="6" class="pl-5">
                          <h4 class="primary--text">Start time:</h4>
                      </v-col>
                      <v-col cols="6">
                        <h4>18:30:15</h4>
                      </v-col>                      
                    </v-row> 

                    <v-row dense>
                      <v-col cols="6" class="pl-5">
                          <h4 class="primary--text">Remaining time:</h4>
                      </v-col>
                      <v-col cols="6">
                        <h4 class="">2:25:10</h4>
                      </v-col>                      
                    </v-row>
                    <br>
                    <hr>
                    
                    <v-card-text class="text-subtitle-1 font-weight-bold">{{
                      "IO Status:"
                    }}</v-card-text>
                    <v-row dense>
                        
                    </v-row>

                    
                    <v-card-text class="text-subtitle-1 font-weight-bold">{{
                      "Warning Messages:"
                    }}</v-card-text>

                  </v-card>
                </v-container>
              </v-tab-item>

              
            </v-tabs-items>
          </v-card>
          </v-layout>
        </v-col>

        <v-col cols="6">
          <v-layout column align-center>
          <!-- <v-card class="pa-2" outlined> cam</v-card> -->
          <v-card>
            <v-tabs
              v-model="tab"
              background-color="light-blue"
              dark
              centered
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
        </v-layout>       
        
        </v-col>

        <v-col cols="3">
          <v-layout column align-center>
          <v-card>
            <v-tabs
              v-model="controlTab"
              background-color="light-blue"
              dark
              centered
              class="pa-1"
              outlined
            >
              <v-tabs-slider color="yellow"></v-tabs-slider>
              <v-tab v-for="control in controls" :key="control.tab">
                {{ control.tab }}
              </v-tab>
            </v-tabs>

            <v-tabs-items v-model="controlTab">
              <!-- Joy Software -->
              <v-tab-item>
                <v-container>
                  <v-card
                    height="480px"
                    width="300px"
                    class="light-blue lighten-5"
                  >
                    <v-card-text class="text-subtitle-1 font-weight-bold">{{
                      "Joy Software:"
                    }}</v-card-text>
                    <v-row  class="px-2">
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

                    <v-row  dense>
                      <v-col class="d-flex justify-center" cols="4"></v-col>
                      <v-col class="d-flex justify-center" cols="4">
                        <v-btn large class="light-blue accent-4">FW</v-btn>
                      </v-col>
                      <v-col class="d-flex justify-center" cols="4"></v-col>
                    </v-row>

                    <v-row  dense>
                      <v-col class="d-flex justify-end" cols="4">
                        <v-btn large class="light-blue accent-4">TL</v-btn>
                      </v-col>
                      <v-col class="d-flex justify-center" cols="4">
                        <v-btn large class="light-blue accent-4"></v-btn>
                      </v-col>
                      <v-col class="d-flex justify-start" cols="4">
                        <v-btn large class="light-blue accent-4">TR</v-btn>
                      </v-col>
                    </v-row>

                    <v-row  dense>
                      <v-col class="d-flex justify-center" cols="4"></v-col>
                      <v-col class="d-flex justify-center" cols="4">
                        <v-btn large class="light-blue accent-4">BW</v-btn>
                      </v-col>
                      <v-col class="d-flex justify-center" cols="4"></v-col>
                    </v-row>

                    <br />
                    <hr />
                    <!-- <v-divider></v-divider> -->

                    <v-row  dense class="px-5">
                      <v-radio-group v-model="radios">
                        <template v-slot:label>
                          <div>Selected <strong>Running Mode</strong></div>
                        </template>
                        <v-radio value="Auto Mode">
                          <template v-slot:label>
                            <div>
                              <strong class="success--text">Auto mode</strong>
                            </div>
                          </template>
                        </v-radio>
                        <v-radio value="Manual Mode">
                          <template v-slot:label>
                            <div>
                              <strong class="primary--text">Manual mode</strong>
                            </div>
                          </template>
                        </v-radio>
                      </v-radio-group>
                    </v-row>
                  </v-card>
                </v-container>
              </v-tab-item>

              <!-- Camera ontrl -->
              <v-tab-item>
                <v-container>
                  <v-card
                    height="480px"
                    width="300px"
                    class="light-blue lighten-4"
                  >
                    <v-card-text class="text-subtitle-1 font-weight-bold">{{
                      "PTZ Camera:"
                    }}</v-card-text>

                    <!-- ptz:pan control -->
                    <v-row  class="px-2">
                      <v-col class="d-flex justify-center" cols="12" sm="12">
                        <v-slider
                          v-model="pans.val"
                          :label="pans.label"
                          :thumb-color="pans.color"
                          :thumb-size="24"
                          thumb-label="always"
                        >
                        </v-slider>
                      </v-col>
                    </v-row>

                    <!-- ptz:tilt control -->
                    <v-row  class="px-2">
                      <v-col class="d-flex justify-center" cols="12" sm="12">
                        <v-slider
                          v-model="tilts.val"
                          :label="tilts.label"
                          :thumb-color="tilts.color"
                          :thumb-size="24"
                          thumb-label="always"
                        >
                        </v-slider>
                      </v-col>
                    </v-row>

                    <!-- ptz:zoom control -->
                    <v-row  class="px-2">
                      <v-col class="d-flex justify-center" cols="12" sm="12">
                        <v-slider
                          v-model="zooms.val"
                          :label="zooms.label"
                          :thumb-color="zooms.color"
                          :thumb-size="24"
                          thumb-label="always"
                        >
                        </v-slider>
                      </v-col>
                    </v-row>
                  </v-card>
                </v-container>
              </v-tab-item>

              <!-- IO Control -->
              <v-tab-item>
                <v-container>
                  <v-card
                    height="480px"
                    width="300px"
                    class="light-blue lighten-3"
                  >
                    <!-- <v-card-text>{{ item.content }}</v-card-text> -->
                    <v-card-text class="text-subtitle-1 font-weight-bold">{{
                      "IO Control"
                    }}</v-card-text>
                    <v-row  class="px-5" no-gutters>
                      <v-col class="d-flex justify-start" cols="12" sm="12">
                        <v-switch
                          v-model="waterPumpSwitch"
                          inset
                          color="primary"
                          label="Water Pump Switch"
                        ></v-switch>
                      </v-col>
                    </v-row>

                    <v-row  class="px-5" no-gutters>
                      <v-col class="d-flex justify-start" cols="12" sm="12">
                        <v-switch
                          v-model="frontLightSwitch"
                          inset
                          color="primary"
                          label="Front Light Switch"
                          
                        ></v-switch>
                      </v-col>
                    </v-row>

                    <v-row  class="px-5 py-1" no-gutters>
                      <v-col class="d-flex justify-start" cols="12" sm="12">
                        <v-switch
                          v-model="rearLightSwitch"
                          inset
                          color="primary"
                          label="Rear Light Switch"
                        ></v-switch>
                      </v-col>
                    </v-row>

                    <v-row  class="px-5" no-gutters>
                      <v-col class="d-flex justify-start" cols="12" sm="12">
                        <v-switch
                          v-model="magneticSwitch"
                          inset
                          color="primary"
                          label="Magnetic Switch"
                        ></v-switch>
                      </v-col>
                    </v-row>

                    <v-row  class="px-5" no-gutters>
                      <v-col class="d-flex justify-start" cols="12" sm="12">
                        <v-switch
                          v-model="motorDriveSwitch"
                          inset
                          color="primary"
                          label="Motor Drive Switch"
                        ></v-switch>
                      </v-col>
                    </v-row>

                    <v-row  class="px-5" no-gutters>
                      <v-col class="d-flex justify-start" cols="12" sm="12">
                        <v-switch
                          v-model="motorBreakSwitch"
                          inset
                          color="primary"
                          label="Motor Break Switch"
                        ></v-switch>
                      </v-col>
                    </v-row>
                  </v-card>
                </v-container>
              </v-tab-item>
            </v-tabs-items>
          </v-card>
          </v-layout>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "HomeView",
  components: {},
  data: () => ({
    tab: null,
    controlTab: null,
    workTab: null,
    items: [
      { tab: "All", content: "Tab 1 Content" },
      { tab: "Camera 1", content: "Tab 2 Content" },
      { tab: "Camear 2", content: "Tab 3 Content" },
      { tab: "PTZ Camera", content: "Tab 4 Content" },
      { tab: "Map", content: "Tab 5 Content" },
    ],
    controls: [
      { tab: "JOY", content: "Joy Software Content" },
      { tab: "PTZ", content: "PTZ Control Content" },
      { tab: "IO", content: "IO Control Content" },
    ],
    works: [
      { tab: "Details", content: "Work Content" },
      { tab: "Status", content: "Status Content" },
    ],
    speedItems: ["Faster", "Fast", "Medium", "Slow", "Slower"],
    pans: { label: "Pan", val: 50, color: "red" },
    tilts: { label: "Tilt", val: 50, color: "green" },
    zooms: { label: "Zoom", val: 50, color: "blue" },
    waterPumpSwitch: false,
    frontLightSwitch: false,
    rearLightSwitch: false,
    magneticSwitch: false,
    motorDriveSwitch: false,
    motorBreakSwitch: false,
    radios: "Auto Mode",
  }),
  // data() {
  //   return {
  //     tab: null,
  //     //items: ["All Camera", "Camera 1", "Camear 2", "PTZ Camear"],
  //     text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
  //     items: [
  //       { tab: "All", content: "Tab 1 Content" },
  //       { tab: "Camera 1", content: "Tab 2 Content" },
  //       { tab: "Camear 2", content: "Tab 3 Content" },
  //       { tab: "PTZ Camera", content: "Tab 4 Content" },
  //       { tab: "Map", content: "Tab 5 Content" },
  //     ],
  //   speedItems:['Faster', 'Fast', 'Medium', 'Slower', 'Slow'],

  //   };
  // },
};
</script>
