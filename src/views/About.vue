<template>
  <v-container fluid>
    <v-slide-y-transition mode="out-in">
      <v-layout row wrap
        justify-center
        class="mt-3"
      >
         <v-flex xs10 lg8 class="mb-4">
          <v-card>
            <v-card-title
              primary-title
              class="title accent secondary--text">
              Who We Are
            </v-card-title>
            <v-card-text>
              <v-layout
                row wrap
                justify-start
                v-for="(person, ind) in members"
                class="mb-4"
                :key="ind"
              >
                <v-flex xs1>
                  <v-avatar>
                    <v-icon x-large="">account_circle</v-icon>
                  </v-avatar>
                </v-flex>
                <v-flex xs10>
                  <h1 class="display-2 primary--text">John Smith</h1>
                </v-flex>
                <v-flex xs10 class="ml-3 mt-1">
                  <p v-text="person.bio"></p>
                </v-flex>
              </v-layout>
            </v-card-text>
          </v-card>
        </v-flex>
        <v-flex xs10 lg8 class="mb-4">
          <v-card>
            <v-card-title
              primary-title
              class="title accent secondary--text">
              Our Mission Statement
            </v-card-title>
            <v-card-text>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-slide-y-transition>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      members: [
        {
          name: 'John Smith',
          bio: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.'
        },
        {
          name: 'Other Person',
          bio: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.mission {
  height: 60vh;
}
</style>
