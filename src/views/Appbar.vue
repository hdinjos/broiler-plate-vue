<template>
  <!-- <v-app>
  </v-app>-->
  <div>
    <v-row no-gutters>
      <v-col cols="12" xs="12" md="6" class="pr-4">
        <p class="mb-1 pa-0">Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, officia quasi minima ullam, vel quia provident expedita voluptate rem temporibus tempora unde necessitatibus asperiores excepturi eveniet? Dolor eius nesciunt voluptate?</p>
        <p class="mb-1 pa-0">The v-list component is used to display information. It can contain an avatar, content, actions, subheaders and much more. Lists present content in a way that makes it easy to identify a specific item in a collection. They provide a consistent styling for organizing groups of text and images.</p>
        <p class="mb-1 pa-0">Out of the box you get access to all colors in the Material Design spec through sass and javascript. These values can be used within your style sheets, your component files and on actual components via the color class system.</p>
      </v-col>
      <v-col cols="12" xs="12" md="6" justify="center">
        <v-expansion-panels inset>
          <v-expansion-panel v-for="project in myProjects" :key="project.title">
            <v-expansion-panel-header>{{project.title}}</v-expansion-panel-header>
            <v-expansion-panel-content>
              {{project.content}}
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-col>
    </v-row>
    <v-row no-gutters></v-row>
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
        },
        {
          title: "Belajar Module NodeJs Lagi",
          person: "Roby",
          due: "25 April 2019",
          status: "Selesai",
          content:
            "As an asynchronous event-driven JavaScript runtime, Node.js is designed to build scalable network applications. In the following 'hello world' example, many connections can be handled concurrently. Upon each connection, the callback is fired, but if there is no work to be done, Node.js will sleep."
        }
      ]
    };
  },
  methods: {

  },
  computed: {
    myProjects(){
      return this.projects.filter(project => project.person === "Roby")
    }
  }
};
</script>
