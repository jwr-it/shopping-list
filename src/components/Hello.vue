<template>
  <v-container grid-list-md>
    <v-layout row wrap>
      <v-flex xs12>
        <v-card color="primary">
          <v-card-text class="px-0 py-0 title white--text">
              <v-subheader inset dark class="title white--text center-xs-text">Biedronka</v-subheader>
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

          <v-divider light></v-divider>
          <v-subheader inset dark class="title white--text center-xs-text">Kupione</v-subheader>

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
