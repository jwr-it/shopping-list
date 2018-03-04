<template>
    <v-app>
        <v-navigation-drawer
        fixed
        :clipped="$vuetify.breakpoint.mdAndUp"
        app
        v-model="drawer"
        >

        <v-layout wrap>
            <v-flex xs12>
                <v-divider></v-divider>
                <v-text-field
                prepend-icon="search"
                label="Search or add shop"
                single-line
                full-width
                hide-details
                flat
                class="mx-2"
                ></v-text-field>
            </v-flex>
        </v-layout>

        <v-divider></v-divider>
        <v-list class="pt-0">
            <v-list-tile v-for="(item, i) in items" :key="i" @click="">
                <v-list-tile-avatar>
                    <v-icon>{{ item.icon }}</v-icon>
                </v-list-tile-avatar>
                <v-list-tile-content>
                    <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                </v-list-tile-content>
                <v-list-tile-action>
                    <v-btn flat icon>
                        <v-icon>visibility_off</v-icon>
                    </v-btn>
                </v-list-tile-action>
            </v-list-tile>
        </v-list>
        <v-divider></v-divider>


        <v-list>
          <v-list-group
            no-action
          >
            <v-list-tile slot="activator">
                <v-list-tile-avatar>
                    <v-icon>visibility_off</v-icon>
                </v-list-tile-avatar>

              <v-list-tile-content>
                <v-list-tile-title>Hidden</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <v-list-tile v-for="item in items" :key="item.title" @click="">
              <v-list-tile-content>
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile-content>
              <v-list-tile-action>
                  <v-menu bottom offset-y>
                    <v-btn flat icon slot="activator">
                        <v-icon>more_vert</v-icon>
                    </v-btn>
                    <v-list>

                      <v-list-tile @click="">
                          <v-icon>visibility</v-icon>
                          <v-list-title>Show</v-list-title>
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
          </v-list-group>
        </v-list>


    </v-navigation-drawer>


    <v-toolbar
    dark
    app
    :clipped-left="$vuetify.breakpoint.mdAndUp"
    class="primary"
    fixed
    >
    <v-toolbar-title>
        <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
        <span v-text="title"></span>
    </v-toolbar-title>
</v-toolbar>
<v-content>

    <router-view/>

</v-content>
<v-footer :fixed="fixed" app>
    <span>&copy; 2018</span>
</v-footer>
</v-app>
</template>

<script>
import Vue from 'vue'
export default {
    data () {
        return {
            cordova: Vue.cordova,
            drawer: null,
            items: [
                {
                    icon: 'store',
                    title: 'Centrum'
                },
                {
                    icon: 'store',
                    title: 'Biedronka'
                },
                {
                    icon: 'store',
                    title: 'Unimet'
                },
                {
                    icon: 'store',
                    title: 'Apteka'
                },
            ],

            miniVariant: false,
            right: true,
            rightDrawer: false,
            title: 'Shopping list',
            fixed: true
        }
    },
    created () {
        var self = this
        this.cordova.on('deviceready', () => {
            self.onDeviceReady()
        })
    },
    methods: {
        onDeviceReady: function () {
            // Handle the device ready event.
            this.cordova.on('pause', this.onPause, false)
            this.cordova.on('resume', this.onResume, false)
            if (this.cordova.device.platform === 'Android') {
                document.addEventListener('backbutton', this.onBackKeyDown, false)
            }
        },
        onPause () {
            // Handle the pause lifecycle event.
            console.log('pause')
        },
        onResume () {
            // Handle the resume lifecycle event.
            // SetTimeout required for iOS.
            setTimeout(function () {
                console.log('resume')
            }, 0)
        },
        onBackKeyDown () {
            // Handle the back-button event on Android. By default it will exit the app.
            navigator.app.exitApp()
        }
    }
}
</script>

<style lang="stylus">
@import './stylus/main.styl'
</style>

<style>
body {
    padding-top: constant(safe-area-inset-top);
    padding-top: env(safe-area-inset-top);
}
.footer{ /* Apply this to v-bottom-nav if necessary. */
    margin-bottom: constant(safe-area-inset-bottom);
    margin-bottom: env(safe-area-inset-bottom);
}
</style>
