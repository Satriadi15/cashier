<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="SideDrawer"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in sideMenu"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-toolbar-title v-text="title" />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>  
      <v-bottom-navigation 
      horizontal
      height="10vh"
      fixed
      color="primary"
      app
      >
        <v-app-bar-nav-icon @click.stop="SideDrawer = !SideDrawer" />
          <v-btn v-for="(item, i) in bottomMenu"
                 :key="i"
                 :to="item.to">
                 <span>{{ item.title }}</span>
                 <v-icon>{{ item.icon }}</v-icon>
          </v-btn>
      <v-spacer />
      </v-bottom-navigation>       
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      SideDrawer: false,
      sideMenu: [
        {
          icon: 'mdi-account',
          title: 'Account',
          to: '/account',
        },
         {
          icon: 'mdi-bell',
          title: 'Notification',
          to: '/notification',
        },
      ],bottomMenu: [
        {
          icon: 'mdi-application',
          title: 'App',
          to: '/',
        },
      ],
      right: true,
      title: 'Cashier',
    }
  },
}
</script>
