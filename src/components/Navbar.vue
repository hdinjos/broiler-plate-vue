<template>
  <v-app>
    <v-app-bar app flat color="pink lighten-1" dark>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Application</v-toolbar-title>
      <v-spacer></v-spacer>

      <!-- dropdown menu -->
      <div class="pr-2">
        <v-menu offset-y transition="scale-transition">
          <template v-slot:activator="{on}">
            <v-btn dense color="white pink--text" dark v-on="on">
              <v-icon left>mdi-chevron-down</v-icon>
              <span>Menu</span>
            </v-btn>
          </template>
          <v-list dense>
            <v-list-item link v-for="item in items" :key="item.title" router :to="item.router">
              <v-list-item-title>{{item.title}}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </div>

      <v-btn dense color="white pink--text" light>
        <span>Keluar</span>
        <v-icon right>mdi-logout-variant</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" fixed app>
      <!-- <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>John Leider</v-list-item-title>
        </v-list-item-content>
      </v-list-item>-->
      <v-row no-gutters>
        <v-col class="mt-5" justify="center" align="center">
          <v-avatar size="100">
            <img src="/06.png" />
          </v-avatar>
          <p class="title pt-1">New Avatar</p>
        </v-col>
      </v-row>
      <v-row no-gutters>
        <v-col>
          <Popup />
        </v-col>
      </v-row>

      <v-divider></v-divider>

      <v-list dense>
        <!-- group pertama -->
        <v-list-group
          v-for="item in items"
          :key="item.title"
          v-model="item.active"
          :prepend-icon="item.action"
          no-action
        >
          <!-- membuat nested dari group pertama-->
          <template v-slot:activator>
            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </template>

          <!-- group 2 sub dari group pertama -->
          <v-list-group v-for="subItem in item.items" :key="subItem.title" no-action sub-group>
            <!-- membuat nested list dari sub group -->
            <template v-slot:activator>
              <v-list-item-content>
                <v-list-item-title v-text="subItem.title"></v-list-item-title>
              </v-list-item-content>
            </template>
            <!-- isi dari list dari subgroup pertama / group kedua -->
            <v-list-item v-for="list in subItem.lists" :key="list.title" router :to="list.router">
              <v-list-item-title v-text="list.title"></v-list-item-title>
            </v-list-item>
          </v-list-group>
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
import Popup from "./Popup";

export default {
  components: {
    Popup
  },
  data() {
    return {
      drawer: false,
      items: [
        {
          action: "mdi-account",
          title: "Account",
          router: "/",
          active: true,
          items: [
            {
              title: "Account 1",
              lists: [{ title: "Man", router: "/about" }, { title: "Woman" }]
            }
          ]
        },
        {
          action: "mdi-clipboard-check",
          title: "Task",
          router: "/about",
          items: [
            {
              title: "Read & Write",
              lists: [
                { title: "Book", router: "/card" },
                { title: "Blog", router: "/" },
                { title: "Narasi" }
              ]
            },
            {
              title: "Ngoding",
              lists: [{ title: "Javascript", router: "/date" }]
            },
            { title: "Rest" }
          ]
        },
        {
          action: "mdi-cube-outline",
          title: "Project",
          router: "/appbar",
          items: [
            {
              title: "Waiting List",
              lists: [
                { title: "SteamDOM" },
                { title: "Logistic App", router: "/appbar" }
              ]
            }
          ]
        }
      ]
    };
  }
};
</script>
