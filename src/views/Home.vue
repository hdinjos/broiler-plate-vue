<template>
  <div class="mx-5">
    <v-row no-gutters class="mb-3">
      <v-col cols="6" md="2">
        <v-tooltip bottom>
          <template v-slot:activator="{on}">
            <v-btn v-on="on" small dark text color="grey" @click="sortBy('title')">
              <v-icon left>mdi-folder</v-icon>
              <span class="caption text-lowercase">by project name</span>
            </v-btn>
          </template>
          <span>Sort projects name by project title</span>
        </v-tooltip>
      </v-col>
      <v-col cols="6" md="10">
        <v-tooltip bottom>
          <template v-slot:activator="{on}">
            <v-btn v-on="on" small dark text color="grey" @click="sortBy('person')">
              <v-icon left>mdi-account</v-icon>
              <span class="caption text-lowercase">by person</span>
            </v-btn>
          </template>
          <span>Sort projects by person</span>
        </v-tooltip>
      </v-col>
    </v-row>
    <v-card flat tile v-for="project in projects" :key="project.title">
      <!-- <v-layout row wrap>
        this can use xs breakpoint coz version 1
        <v-flex xs12 md6>
          <div class="caption grey--text">Project Title</div>
          <div>Create a new website</div>
        </v-flex>
        <v-flex xs4 md2>
          <div class="caption grey--text">Person</div>
          <div>Ninja net</div>
        </v-flex>
        <v-flex xs4 md2>
          <div class="caption grey--text">Due by</div>
          <div>24 Desember 2019</div>
        </v-flex>
        <v-flex xs4 md2>
          <div class="caption grey--text">Status</div>
          <div>Success</div>
        </v-flex>
      </v-layout>-->
      <v-row :class="`pa-3 project ${project.status}`" no-gutters>
        <!-- cols change the xs breakpoint, coz this version 2 of veutify -->
        <v-col cols="12" md="6">
          <div class="caption grey--text">Project Title</div>
          <div>{{project.title}}</div>
        </v-col>
        <v-col cols="4" md="2">
          <div class="caption grey--text">Person</div>
          <div>{{project.person}}</div>
        </v-col>
        <v-col cols="4" md="2">
          <div class="caption grey--text">Due By</div>
          <div>{{project.due}}</div>
        </v-col>
        <v-col cols="4" md="2">
          <!-- <div class="caption grey--text">Status</div>
          <div>{{project.status}}</div>-->
          <div class="d-flex justify-end">
            <v-chip small :class="`${project.status} white--text caption my-2`">{{project.status}}</v-chip>
          </div>
        </v-col>
      </v-row>
      <v-divider></v-divider>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Belajar Machine Learning Python",
          person: "Choliss",
          due: "23 April 2019",
          status: "Ongoing",
          content:
            "Machine learning is a type of artificial intelligence (AI) that provides computers with the ability to learn without being explicitly programmed. Machine learning focuses on the development of Computer Programs that can change when exposed to new data. In this article, we’ll see basics of Machine Learning, and implementation of a simple machine learning algorithm using python."
        },
        {
          title: "Belajar VueJs Framework",
          person: "Yoga",
          due: "24 April 2019",
          status: "Proses",
          content:
            "Vue (pronounced /vjuː/, like view) is a progressive framework for building user interfaces. Unlike other monolithic frameworks, Vue is designed from the ground up to be incrementally adoptable. The core library is focused on the view layer only, and is easy to pick up and integrate with other libraries or existing projects. On the other hand, Vue is also perfectly capable of powering sophisticated Single-Page Applications when used in combination with modern tooling and supporting libraries."
        },
        {
          title: "Belajar Module NodeJs",
          person: "Roby",
          due: "25 April 2019",
          status: "Selesai",
          content:
            "As an asynchronous event-driven JavaScript runtime, Node.js is designed to build scalable network applications. In the following 'hello world' example, many connections can be handled concurrently. Upon each connection, the callback is fired, but if there is no work to be done, Node.js will sleep."
        },
        {
          title: "Belajar Java OOP",
          person: "Jarig",
          due: "23 April 2019",
          status: "Proses",
          content:
            "Procedural programming is about writing procedures or methods that perform operations on the data, while object-oriented programming is about creating objects that contain both data and methods."
        }
      ]
    };
  },
  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => (a[prop] < b[prop] ? -1 : 1));
    }
  }
};
</script>

<style scoped>
.project.Ongoing {
  border-left: 4px solid blueviolet;
}
.project.Proses {
  border-left: 4px solid palevioletred;
}
.project.Selesai {
  border-left: 4px solid green;
}
.theme--light.v-chip.Ongoing {
  background: blueviolet;
}
.theme--light.v-chip.Proses {
  background: palevioletred;
}
.theme--light.v-chip.Selesai {
  background: green;
}
</style>
