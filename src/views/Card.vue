<template>
  <div>
    <v-row>
      <v-col cols="12" sm="6" md="4" lg="3" v-for="person in team" :key="person.name">
        <v-card flat class="text-center ma-3">
          <v-responsive class="pt-4">
            <v-avatar size="100" class="pink">
              <img :src="person.avatar" alt="">
            </v-avatar>
          </v-responsive>
          <v-card-text>
            <div class="headline">{{person.name}}</div>
            <div class="grey--text">{{person.role}}</div>
          </v-card-text>
          <v-card-actions>
            <v-btn small text flat color="grey" dark>
              <v-icon small left>mdi-message</v-icon>
              <span>Message</span>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      team: [
        { name: "Eko", role: "Java Developer", avatar: "/01.png" },
        { name: "Agus", role: "Flutter Developer", avatar: "/02.png" },
        { name: "Rama", role: "Python Developer", avatar: "/03.png" },
        { name: "Nisa", role: "Ecma Script Developer", avatar: "/04.png" },
        { name: "Dara", role: "Fullstack", avatar: "/05.png" }
      ]
    };
  }
};
</script>
<style scoped>
</style>