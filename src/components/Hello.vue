<template>
  <v-container fluid grid-list-md>
    <v-layout row wrap>
      <v-flex xs12>
        <v-card color="secondary">
          <v-card-text class="px-0 py-0">
              <v-subheader inset dark class="title black--text">Biedronka</v-subheader>
          </v-card-text>
          <v-list two-line subheader>
            <v-list-tile avatar>
              <v-list-tile-action>
                <v-checkbox v-model="notifications"></v-checkbox>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>Notifications</v-list-tile-title>
                <v-list-tile-sub-title>Allow notifications</v-list-tile-sub-title>
              </v-list-tile-content>
              <v-list-tile-action>



                    <div class="text-xs-center hidden-sm-and-down">
                        <v-btn fab dark small color="accent">
                          <v-icon dark>arrow_downward</v-icon>
                        </v-btn>
                      <v-btn fab dark small color="accent">
                        <v-icon dark>arrow_upward</v-icon>
                      </v-btn>

                      <v-btn fab dark small color="error">
                        <v-icon dark>delete</v-icon>
                      </v-btn>

                    </div>
                  



                  <v-menu bottom offset-y class="hidden-md-and-up">
                    <v-btn flat icon slot="activator">
                        <v-icon>more_vert</v-icon>
                    </v-btn>
                    <v-list>
                      <v-list-tile @click="">
                          <v-icon>arrow_upward</v-icon>
                          <v-list-title>Up</v-list-title>
                      </v-list-tile>
                      <v-list-tile @click="">
                          <v-icon>arrow_downward</v-icon>
                          <v-list-title>Down</v-list-title>
                      </v-list-tile>

                      <v-divider></v-divider>
                      <v-list-tile @click="">
                        <v-list-tile-title>
                            <v-icon>delete</v-icon>
                            <v-list-title>Delete</v-list-title>
                        </v-list-tile-title>
                      </v-list-tile>

                    </v-list>
                  </v-menu>
              </v-list-tile-action>
            </v-list-tile>
            <v-list-tile avatar>
              <v-list-tile-action>
                <v-checkbox v-model="sound"></v-checkbox>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>Sound</v-list-tile-title>
                <v-list-tile-sub-title>Hangouts message</v-list-tile-sub-title>
              </v-list-tile-content>
            </v-list-tile>
            <v-list-tile avatar>
              <v-list-tile-action>
                <v-checkbox v-model="video"></v-checkbox>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>Video sounds</v-list-tile-title>
                <v-list-tile-sub-title>Hangouts video call</v-list-tile-sub-title>
              </v-list-tile-content>
            </v-list-tile>
            <v-list-tile avatar>
              <v-list-tile-action>
                <v-checkbox v-model="invites"></v-checkbox>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>Invites</v-list-tile-title>
                <v-list-tile-sub-title>Notify when receiving invites</v-list-tile-sub-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list>

          <v-divider ></v-divider>


          <v-layout row wrap>
                <v-flex xs11>
                    <v-text-field
                      prepend-icon="add_shopping_cart"
                      label="Name"
                      class="mx-3"
                      flat
                      hide-details="true"
                    ></v-text-field>
                </v-flex>

        </v-layout>
          <v-btn block color="teal" dark><v-icon>add</v-icon>Add new</v-btn>

          <v-divider ></v-divider>

          <v-subheader inset dark class="title black--text">Kupione</v-subheader>

          <v-list>
            <v-list-tile>
              <v-list-tile-action>
                <v-checkbox v-model="notifications"></v-checkbox>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title class="striked grey--text">Notifications</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <v-list-tile>
              <v-list-tile-action>
                <v-checkbox v-model="sound"></v-checkbox>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title class="striked grey--text">Sound</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list>

        </v-card>
        <v-btn
            bottom
            right
            fab
            dark
            fixed color="teal">
          <v-icon dark>reorder</v-icon>
        </v-btn>

      </v-flex>
    </v-layout>
  </v-container>
</template>

<style lang="stylus">
.striked {
    text-decoration: line-through;
}
</style>
