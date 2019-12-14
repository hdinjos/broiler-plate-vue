<template>
  <v-app>
      <v-app-bar app flat color="pink lighten-1" dark>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
        <v-toolbar-title>Application</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn color="white pink--text" light>
          <span>Keluar</span>
          <v-icon right>mdi-logout-variant</v-icon>
        </v-btn>
      </v-app-bar>

    <v-navigation-drawer v-model="drawer" fixed app>
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>John Leider</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-group
          v-for="item in items"
          :key="item.title"
          v-model="item.active"
          :prepend-icon="item.action"
          no-action
        >
          <template v-slot:activator>
            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </template>

          <v-list-item
            v-for="subItem in item.items"
            :key="subItem.title"
            router
            :to="subItem.router"
          >
            <v-list-item-content>
              <v-list-item-title v-text="subItem.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
    <v-content>
      <v-container fluid>
      <router-view></router-view>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      items: [
        {
          action: "mdi-account",
          title: "Account",
          active: true,
          items: [{ title: "Account 1", router: "/about" }],
        },
        {
          action: "mdi-clipboard-check",
          title: "Task",
          items: [
            { title: "Read & Write", router: "/" },
            { title: "Ngoding" },
            { title: "Rest" }
          ]
        },
        {
          action: "mdi-cube-outline",
          title: "Project",
          items: [{ title: "Waiting List", router: "/appbar" }]
        }
      ]
    };
  }
};
</script>
