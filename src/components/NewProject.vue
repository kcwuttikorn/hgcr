<template>
  <v-row justify="center">
    <v-dialog
      v-model="dialog"
      fullscreen
      hide-overlay
      transition="dialog-bottom-transition"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn color="primary" dark v-bind="attrs" v-on="on">
          New Project
        </v-btn>
      </template>
      <v-card>
        <v-toolbar dark color="primary">
          <v-btn icon dark @click="dialog = false">
            <v-icon>mdi-close</v-icon>
          </v-btn>
          <v-toolbar-title>Settings</v-toolbar-title>
          <v-spacer></v-spacer>
          <!-- <v-toolbar-items>
            <v-btn dark text @click="dialog = false"> Save </v-btn>
          </v-toolbar-items> -->
        </v-toolbar>

        <v-stepper v-model="e1">
          <v-stepper-header>
            <v-stepper-step :complete="e1 > 1" step="1">
              Station & Unit Name
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step :complete="e1 > 2" step="2">
              Generator Information
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step step="3"> Name of step 3 </v-stepper-step>
          </v-stepper-header>

          <v-stepper-items>
            <v-stepper-content step="1">
              <v-card class="mb-12" color="grey lighten-4" height="400px">
                <v-card-text>
                  <v-form class="px-3" ref="stationForm">
                    <h3 class="primary--text">Station and Unit Name:</h3>
                    <v-text-field
                      label="Station name:"
                      v-model="stationName"
                      prepend-icon="mdi-pencil-outline"
                      required
                      :rules="nameRules"
                    ></v-text-field>
                    <v-text-field
                      label="Unit name:"
                      v-model="unitName"
                      prepend-icon="mdi-pencil-outline"
                      :rules="nameRules"
                      required
                    ></v-text-field>

                    <h3 class="primary--text pt-3">Machine Type:</h3>
                    <!-- <p>{{ machineType || 'null' }}</p> -->
                    <v-radio-group v-model="machineType" row mandatory>
                      <v-radio label="Hydro" value="hydro"></v-radio>
                      <v-radio label="Turbo" value="turbo"></v-radio>
                    </v-radio-group>

                    <h3 class="primary--text pt-3">Cleaning Date:</h3>
                    <!-- <p>{{date}}</p> -->
                    <v-menu
                      v-model="menu2"
                      :close-on-content-click="false"
                      :nudge-right="40"
                      transition="scale-transition"
                      offset-y
                      min-width="auto"
                    >
                      <template v-slot:activator="{ on, attrs }">
                        <v-text-field
                          v-model="date"
                          label="Cleaning date"
                          prepend-icon="mdi-calendar"
                          readonly
                          v-bind="attrs"
                          v-on="on"
                        ></v-text-field>
                      </template>
                      <v-date-picker
                        v-model="date"
                        @input="menu2 = false"
                      ></v-date-picker>
                    </v-menu>
                  </v-form>
                </v-card-text>
              </v-card>

              <!-- <v-btn
          text
          color="primary"          
        >
          Back
        </v-btn> -->

              <v-btn text color="primary" @click="e1 = 2"> Next </v-btn>
            </v-stepper-content>

            <v-stepper-content step="2">
              <v-card
                class="mb-12"
                color="grey lighten-4"
                height="400px"
              ></v-card>

              <v-btn text color="primary" @click="e1 = 1"> Back </v-btn>

              <v-btn text color="primary" @click="e1 = 3"> Next </v-btn>
            </v-stepper-content>

            <v-stepper-content step="3">
              <v-card
                class="mb-12"
                color="grey lighten-4"
                height="400px"
              ></v-card>

              <v-btn text color="primary" @click="e1 = 2"> Back </v-btn>

              <v-btn text color="primary" @click="submit"> Save </v-btn>
            </v-stepper-content>
          </v-stepper-items>
        </v-stepper>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
import axios from "axios";
const baseURL = "http://localhost:3001/projects";
export default {
  name: "NewProject",
  data() {
    return {
      date: new Date(Date.now() - new Date().getTimezoneOffset() * 60000)
        .toISOString()
        .substr(0, 10),
      menu2: false,
      dialog: false,
      e1: 1,
      stationName: "",
      unitName: "",
      machineType: "",
      //valid: 'true',
      nameRules: [
        v => !!v || 'Name is required',
        //v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      projectForm:{
        title: '',
        date: '',
        status: ''
      },
    };
  },
  methods: {
    submit() {
    
      //console.log(this.stationName, this.unitName, this.machineType, this.date);
      this.projectForm.title = this.stationName+'-'+this.unitName;
      this.projectForm.date = this.date;
      this.projectForm.status = "ongoing";
      //console.log(this.id)
      this.$emit("newProject", this.projectForm)
    },
    
    // validate() {
    //   this.$refs.stationForm.validate();
    // },
    // reset() {
    //   this.$refs.stationForm.reset();
    // },
    // resetValidation() {
    //   this.$refs.stationForm.resetValidation();
    // },
  },
};
</script>

<style></style>
