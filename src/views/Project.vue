<template>
  <div class="project">
    <h1 class="subheading grey--text">Project</h1>

    <!-- <v-container class="my-5">
      <v-layout align-end>
      <v-btn color="success">
        <span>New</span>
        <v-icon right>mdi-play</v-icon>
      </v-btn>
      </v-layout>
    </v-container> -->
    <v-layout column align-center>
      <v-flex class="mt-5">
        <NewProject @newProject="addProject" />
      </v-flex>
    </v-layout>

    <v-container class="my-5 grey lighten-4">
      <v-layout row class="mb-3 pr-3 pl-3 pt-3">
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              text
              color="grey"
              @click="sortBy('title')"
              v-bind="attrs"
              v-on="on"
            >
              <v-icon left>mdi-folder</v-icon>
              <span class="caption text-lowercase">By Name</span>
            </v-btn>
          </template>
          <span>Sort by name</span>
        </v-tooltip>

        <!-- <v-space></v-space> -->

        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              text
              color="grey"
              @click="sortBy('date')"
              v-bind="attrs"
              v-on="on"
            >
              <v-icon left>mdi-clock</v-icon>
              <span class="caption text-lowercase">By Date</span>
            </v-btn>
          </template>
          <span>Sort by date</span>
        </v-tooltip>
      </v-layout>

      <v-card
        flat
        scrollable
        class="pa-3"
        v-for="project in projects"
        :key="project.title"
      >
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <!-- <v-flex xs12 md6> -->
          <v-flex xs12 md4>
            <div class="caption grey--text">Project title</div>
            <!-- <div>เขื่อนภูมิพล-unit5</div> -->
            <div class="blue--text">{{ project.title }}</div>
          </v-flex>

          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Cleaning Date</div>
            <!-- <div>24/10/2565</div> -->
            <div class="green--text">{{ project.date }}</div>
          </v-flex>

          <v-flex xs6 sm4 md2>
            <div>
              <v-chip
                small
                class="white--text caption my-2"
                :color="project.status === 'complete' ? 'green' : 'orange'"
              >
                {{ project.status }}
              </v-chip>
            </div>
          </v-flex>

          <v-flex xs6 sm4 md2>
            <div>
              <v-chip 
                small 
                class="white--text caption my-2" 
                color="light-blue"
                
                @click="showProject(project.id)"
              >
                details
              </v-chip>
            </div>
          </v-flex>

          <v-flex xs6 sm4 md2>
            <div>
              <v-chip
                small
                class="white--text caption my-2"
                color="light-green"
                @click="madeReport(project.id)"
              >
                report
              </v-chip>
            </div>
          </v-flex>
        </v-layout>
      </v-card>
    </v-container>
  </div>
</template>

<script>
import axios from "axios";
import NewProject from "@/components/NewProject.vue";
const baseURL = "http://localhost:3001/projects";

export default {
  components: { NewProject},
  data() {
    return {
      projects: [],
      
      //id: 0,
    };
  },
  async created() {
    try {
      const res = await axios.get(baseURL);
      this.projects = res.data;
      //console.log(projects);
      // this.projects.forEach((item, index) => {
      //   if(item.id> this.id) 
      //     this.id = item.id 
      // })
      console.log(this.id)
    } catch (e) {
      console.log(e);
    }
  },

  
  methods: {
    sortBy(prop) {
      //this.projects.sort((a,b) => a[prop] < b[prop] ? -1:1)
      this.projects.sort((a, b) => (a[prop] ? -1 : 1));
    },
    showProject(id){
      console.log(id)
    },
    madeReport(id)
    {
      console.log("Report for project id : " + id)
    },
    async addProject(projectForm) {
      try {
        const res = await axios.post(baseURL, projectForm);

        this.projects = [...this.projects, res.data];

        //console.log(this.projects)
      } catch (e) {
        console.error(e);
      }
    }
    
    
  },
};
</script>

<style>
.project.complete {
  border-left: 4px solid #3cd1c2;
}
.project.ongoing {
  border-left: 4px solid orange;
}
.project.overdue {
  border-left: 4px solid tomato;
}
.v-chip.complete {
  /* border-left: 4px solid #3cd1c2 ; */
  background: #3cd1c2;
}
.v-chip.ongoing {
  background: orange;
}
.v-chip.overdue {
  background: tomato;
}
</style>
