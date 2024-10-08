<template>
  
    <v-app>
     
      <v-app-bar app color="primary" clipped-left>
        <img src="v.png" alt="Logo" class="logo">
        <v-app-bar-title class = "dashboardtitle">Dashboard</v-app-bar-title>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" color = "white" class = "ml-16"></v-app-bar-nav-icon>
        <v-btn
        icon 
        color = "primary"
        elevation = "0">
        <v-icon color = "white">mdi-magnify</v-icon>     
        </v-btn>
        <v-menu
            open-on-hover
            bottom
            offset-y
            transition = "scale-transition">
            <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          elevation="0" 
          v-bind="attrs"
          v-on="on"
          
        >
          <v-icon> mdi-gift-outline</v-icon>
          <div class = "btnstyle">Mega Menu</div>
        </v-btn>
      </template>
      <v-list elevation="0">
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
        </v-menu>
        <v-menu
            open-on-hover
            bottom
            offset-y
            transition = "scale-transition">
            <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          elevation="0" 
          v-bind="attrs"
          v-on="on"
          
        >
          <v-icon> mdi-cog</v-icon>
          <div class = "btnstyle">Settings</div>
        </v-btn>
      </template>
      <v-list elevation = "0">
        <v-list-item
          v-for="(item, i) in items2"
          :key="i"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
        </v-menu>
        <v-menu
            open-on-hover
            bottom
            offset-y
            transition = "scale-transition">
            <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          elevation="0" 
          v-bind="attrs"
          v-on="on"
        
          
        >
          <v-icon> mdi-chart-box</v-icon>
          <div class = "btnstyle">Projects</div>
        </v-btn>
      </template>
      <v-list elevation = "0">
        <v-list-item
          v-for="(item, i) in items3"
          :key="i"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
        </v-menu>
        <v-spacer> </v-spacer>
            <v-btn fab elevation = "0" small color = "indigo lighten-3">
                <v-icon color = "indigo darken-1">
        mdi-dots-grid
      </v-icon>
            </v-btn>
            <v-badge
         top
         outlined
         color = "red"
            dot
          offset-x = "9"
            offset-y = "9">    
            <v-btn fab elevation = "0" small color = "red lighten-3" class = "ml-2">
      <v-icon color = "red darken-1">
        mdi-bell
      </v-icon>
    </v-btn>
</v-badge>

<v-btn fab elevation = "0" small color = "blue-grey lighten-1" class = "ml-2">
      <v-icon>
        mdi-flag
      </v-icon>
    </v-btn>
    <v-btn fab elevation = "0" small color = "green lighten-3" class = "ml-2">
      <v-icon color = "green darken-1">
        mdi-leaf
      </v-icon>
    </v-btn>
       <v-divider vertical class = "ml-4 mr-3" inset></v-divider>
       <v-menu
        bottom
        min-width="200px"
        rounded
        offset-y
      >
        <template v-slot:activator="{ on }">
          <v-btn
         
            icon
            x-large
            v-on="on"
          >
            <v-avatar
              size="40"
            >
            <v-img src = "pfp1.png"></v-img>
            </v-avatar>
          </v-btn>
        </template>
        <v-card>
          <v-list-item-content class="justify-center">
            <div class="mx-auto text-center">
              <v-avatar
               size = "40"
              >
              <v-img src = "pfp1.png"></v-img>
              </v-avatar>
              <h3 class = "pt-3">{{ user.fullName }}</h3>
              <p class="text-caption mt-1">
                {{ user.email }}
              </p>
              <v-divider class="my-3"></v-divider>
              <v-dialog
      v-model="dialog"
      persistent
      max-width="290"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
                depressed
                rounded
                text
                v-bind = "attrs"
                v-on="on"
              >
              
                sign out
              </v-btn>
      </template>
      <v-card>
        <v-card-title class="text-h5">
          Are you sure you want to sign-out?
        </v-card-title>
        <v-card-text>You will have to re-log into the website to continue using your dashboard</v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="black"
            text
            @click="dialog = false"
          >
            Cancel
          </v-btn>
          <v-btn
            color="black"
            text
            to = "/"
          >
            Sign Out
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
              
              <v-divider class="my-3"></v-divider>
              <v-btn
                depressed
                rounded
                text
              >
                terms and condition
              </v-btn>
            </div>
          </v-list-item-content>
        </v-card>
      </v-menu>
    <v-list color = "transparent" width= "190">
        <v-list-item>
        <v-list-item-content>
            <v-list-item-title class = "name1">Darwin Williams</v-list-item-title>
            <v-list-item-subtitle><p  class = "desc1">Senior Software Developer</p></v-list-item-subtitle>
        </v-list-item-content>
    </v-list-item>
    </v-list>
    <v-btn 
    to = "test"
    icon 
    small
    color = "primary"
    elevation = "0">
    <v-icon color = "white">mdi-inbox</v-icon></v-btn>
    
    <v-divider  vertical inset class = "ml-4 mr-4"></v-divider>
    <v-app-bar-nav-icon @click.stop="drawer = !drawer" color = "white" class = "mr-0"></v-app-bar-nav-icon>
      </v-app-bar>
      <v-navigation-drawer v-model="drawer" width = "320" app clipped >
                <div class = "format7">menu</div>
              <v-list>
                <v-list-group v-model="dashboardSubgroupOpen" prepend-icon="mdi-rocket">
                  <template v-slot:activator>
                    <v-list-item-title>Dashboard</v-list-item-title>
                  </template>
                  <v-list-item v-for="(item, index) in dashboardItems" :key="index">
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item>
                </v-list-group>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-note</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Pages</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-layers</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Applications</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <div class = "format8"> ui components</div>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-diamond</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Elements</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-car</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Components</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-table</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Tables</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <div class="format8">Dashboard Widgets</div>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-chart-pie-outline</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Chart Boxes 1</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-routes</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Chart Boxes 2</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-basketball</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Chart Boxes 3</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-map</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Profile Boxes</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <div class = "format8">forms</div>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-lightbulb</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Elements</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-controller</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Widgets</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                  <div class = "format8">charts</div>
                  <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-chart-line</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>ChartJS</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-chart-pie-outline</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Apex Charts</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-chart-line-variant</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>Chart Sparklings</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                
              </v-list>
      </v-navigation-drawer>
      <v-main>
 
        <v-container class = "mt-5">
          <nuxt></nuxt>
        </v-container>
          

       
    
      </v-main>
    </v-app>
  </template>
  
  <script>  
  export default {
  
    name: 'dashboard',
    data() {
       
      return {
       dialog:false,
       drawer: false,
        items: [
        { title: 'cat' },
        { title: 'Test 2' },
        { title: 'Test 3' },
        { title: 'Test 4' },
        ],
        items2: [
        { title: 'dog' },
        { title: 'Test 2' },
        { title: 'Test 3' },
        { title: 'Test 4' },
        ],
        items3: [
        { title: 'horse' },
        { title: 'Test 2' },
        { title: 'Test 3' },
        { title: 'Test 4' },
        ],
        user: {
        fullName: 'Darwin Williams',
        email: 'darwin.williams64@gmail.com',
      },
     
     
       
        
        dashboardSubgroupOpen: false,
        dashboardItems: [
          {
            title: 'Analytics'
          },
          {
            title: 'Commerce'
          },
          {
            title: 'Sales'
          },
          {
            title: 'Minimal'
          },
          {
            title: 'CRM'
          }
        ]
      };
    }
  }
  </script>
  
  <style>
  .logo {
    height: 48px;
    margin-right: 16px;
    padding-left: 15px;
  }
  .format7{
    text-align: left;
    color: blue;
    text-transform: uppercase;
    padding-top: 12px;
    padding-left: 15px;
    margin-bottom: -4%;
    font-weight: 500;
    font-family:system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif
  }

  .format8{

    text-align: left;
    color: blue;
    text-transform: uppercase;
    padding-top: 0px;
    padding-left: 15px;
    margin-bottom: -1%;
    font-weight: 500;
    font-family:system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif
  }
.btnstyle{
    text-transform:none;
    font-weight: 250;
    font-family: Arial, Helvetica, sans-serif;
    padding-left: 7px;
    padding-top: 2px;
    font-weight: 350;
    
}
.spacing {
    margin-left: 2%
}
.dashboardtitle{
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-size: 24pt;
    color: white;
    padding-left: 30px;
}
.name1 {
    color: white;
    font-size: 16pt;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    text-align:left;
    padding-top:12px;
}
.desc1{
    color: white;
    font-size: 8pt;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    text-align: left;
 
}

  </style>