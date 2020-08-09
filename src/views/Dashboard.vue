<template>
  <div class="dashboard">
      <h1 class="subtitle-1 grey--text">Dashboard</h1>

      <v-container class="my-5">
          <v-card flat class="px-3" v-for="(project, index) in projects" :key="project.title" :class="['project', project.status]">
              <v-row>
                  <v-col cols="12" md="6">
                      <div class="caption grey--text">
                          Project Title
                      </div>
                      <div>
                          {{ project.title }}
                      </div>
                  </v-col>
                  <v-col cols="6" sm="4" md="2">
                      <div class="caption grey--text">
                          Person
                      </div>
                      <div>
                          {{ project.person }}
                      </div>
                  </v-col>
                  <v-col cols="6" sm="4" md="2">
                      <div class="caption grey--text">
                          Due by
                      </div>
                      <div>
                          {{ project.due }}
                      </div>
                  </v-col>
                   <v-col cols="12" sm="4" md="2" class="d-flex align-center justify-end">
                        <v-chip small :class="[project.status, 'white--text', 'caption', 'my-2']">
                            {{ project.status }}
                        </v-chip>
                  </v-col>
              </v-row>
              <v-divider v-if="projects.length - index >= 2"></v-divider>
          </v-card>
      </v-container>
  </div>
</template>

<script>
export default {
    data () {
        return {
            projects: [
                { title: 'Design a new website', person: 'The Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
                { title: 'Code up the homepage', person: 'Chun Li', due: '10th Jan 2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
                { title: 'Design video thumbnails', person: 'Ryu', due: '20th Dec 2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
                { title: 'Create a community forum', person: 'Gouken', due: '20th Oct 2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
            ]
        }
    }
}
</script>

<style scoped>
    .project.complete {
        border-left: 4px solid #3cd1c2;
    }

    .project.ongoing {
        border-left: 4px solid orange;
    }

    .project.overdue {
        border-left: 4px solid tomato;
    }

    .theme--light.v-chip:not(.v-chip--active).complete {
        background: #3cd1c2;
    }

    .theme--light.v-chip:not(.v-chip--active).ongoing {
        background: orange;
    }

    .theme--light.v-chip:not(.v-chip--active).overdue {
        background: tomato;
    }
</style>