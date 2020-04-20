<template>

    <nav>
        <v-toolbar flat app class="grey lighten-2">
            <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
             <v-toolbar-title class="text-uppercase grey--text">
                <span class="font-weight-light">Shoppy</span>
                <span class="font-weight-light">GG</span>
                <span> Templates</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn large depressed color="grey lighten-2">
                <span large>Discord</span>
               
               



            </v-btn>
        </v-toolbar>
        
 <v-card
    sticky
    >
    

    <v-navigation-drawer
      v-model="drawer"
      app
      expand-on-hover
      color="grey lighten-3"
      

      
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          
      
            
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
            <v-list-item-icon>
              <v-icon>{{ link.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item>


        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
 
        </v-card>

    </nav>
</template>

<script>

  export default {
    data: () => ({
      drawer: true,
      
      links: [
          { icon: 'mdi-home', text: "Home", route: './home' },
          { icon: 'mdi-account-multiple', text: "About", route: './about' },
          { icon: 'mdi-layers', text: "Templates", route: './templates' },
          { icon: 'mdi-email', text: "Contact", route: './contact' }
      ]

                
    }),
  }
</script>