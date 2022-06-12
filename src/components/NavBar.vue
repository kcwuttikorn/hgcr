<template>
  <nav>
    <v-card>
      <v-app-bar app class="warning lighten-1" dark>
        <v-app-bar-nav-icon
          variant="text"
          icon="mdi-menu"
          class="white--grey"
          @click.stop="drawer = !drawer"
        >
        </v-app-bar-nav-icon>

        <v-toolbar-title class="text-uppercase white--grey">
          <span class="font-weight-light">HCGR</span>
          <span>Gui</span>
        </v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn text color="grey">
          <span>Start</span>
          <v-icon right>mdi-play</v-icon>
        </v-btn>
      </v-app-bar>

      <v-navigation-drawer
        v-model="drawer"
        app
        temporary
        class="warning lighten-1"
      >
        <v-layout column align-center >
          <v-flex class="mt-5">
            <v-avatar size="200">
              <v-img
                src="https://randomuser.me/api/portraits/men/85.jpg"
              ></v-img>
            </v-avatar>         

          </v-flex>
          <!-- <v-list-item>
            <v-list-item-avatar size="200" style="justify-content: center">
              <v-img
                src="https://randomuser.me/api/portraits/men/85.jpg"
              ></v-img>
            </v-list-item-avatar>
          </v-list-item> -->

          <v-list-item>
            <v-list-item-content class="v-list-item_content">
              <v-list-item-title class="text-h5" >HCGR</v-list-item-title>
              <v-list-item-subtitle> SMR</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-layout>

        <!-- <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="text-h6">HCGR</v-list-item-title>
            <v-list-item-subtitle> SMR</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item> -->

        <v-divider></v-divider>

        <v-list>
          <v-list-item
            v-for="link in links"
            :key="link.text"
            link
            router
            :to="link.route"
          >
            <v-list-item-icon>
              <v-icon large>{{ link.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title large>{{ link.text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-card>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      drawer: false,
      group: null,
      links: [
        { icon: "mdi-home", text: "Home", route: "/" },
        { icon: "mdi-new-box", text: "Project", route: "/project" },
        { icon: "mdi-application-cog", text: "Setting", route: "/setting" },
        { icon: "mdi-account-multiple", text: "Contact", route: "/contact" },
      ],
    };
  },
};
</script>

<style>
.v-list-item_content {
  justify-content: center;
  text-align: center;
  display: grid;
}
.v-list-item_avatar {
  justify-items: center;
  align-items: center;
}
</style>
