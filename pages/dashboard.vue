<template>
  <v-row>
    <v-col cols="12">
      <v-row>
        <v-col cols="12" md="12">
          <div class="style1">
            <v-icon color="gray lightened-2"
              >mdi-office-building-outline</v-icon
            >
            Minimal Dashboard
          </div>
        </v-col>
      </v-row>
      <v-row class="mt-n4 mb-n6">
        <v-col cols="12" md="12">
          <v-breadcrumbs :items="items" class="pa-0"> </v-breadcrumbs>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="12">
          <v-card
            color="blue lighten-3"
            outlined
            height="50"
            class="d-flex justify-center align-center"
          >
            <v-icon color="blue darkened-1"> mdi-help-circle</v-icon>
            <div class="help">
              This dashboard was created by Adam Dali using Java Script and
              Veutify without any additonal SCSS
            </div>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="3">
          <v-card class="hello1" elevation="1" min-height="100" outlined>
            <v-card-text>
              <v-row justify="center" align="center">
                <v-col cols="12" sm="6">
                  <h3>NEW ACCOUNTS</h3>

                  <div class="d-flex flex-row">
                    <v-icon color="green accent-3" large class="pt-1"
                      >mdi-chevron-up</v-icon
                    >
                    <div class="mt-2 black--text text1">234%</div>
                  </div>
                </v-col>

                <v-col cols="12" sm="6" class="text-end">
                  <v-progress-circular
                    :rotate="360"
                    :size="60"
                    :width="8"
                    :value="value"
                    color="blue accent-3"
                  >
                    {{ value }}
                  </v-progress-circular>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="3">
          <v-card class="hello2" elevation="1" min-height="100" outlined>
            <v-card-text>
              <v-row justify="center" align="center">
                <v-col cols="12" sm="6">
                  <h3>TOTAL EXPENSES</h3>

                  <div class="d-flex flex-row">
                    <v-icon color="red accent-3" large class="pt-1"
                      >mdi-chevron-down</v-icon
                    >
                    <div class="mt-2 black--text text1">71%</div>
                  </div>
                </v-col>

                <v-col cols="12" sm="6" class="text-end">
                  <v-progress-circular
                    :rotate="360"
                    :size="60"
                    :width="8"
                    :value="value"
                    color="purple accent-3"
                  >
                    {{ value }}
                  </v-progress-circular>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="3">
          <v-card class="hello3" elevation="1" min-height="100" outlined>
            <v-card-text>
              <v-row justify="center" align="center">
                <v-col cols="12" sm="6">
                  <h3>COMPANY VALUE</h3>

                  <div class="d-flex flex-row">
                    <v-icon color="gray lighten-1" large class="pt-1"
                      >mdi-currency-usd</v-icon
                    >
                    <div class="mt-2 black--text text1">1,45M</div>
                  </div>
                </v-col>

                <v-col cols="12" sm="6" class="text-end">
                  <v-progress-circular
                    :rotate="360"
                    :size="60"
                    :width="8"
                    :value="value"
                    color="yellow accent-3"
                  >
                    {{ value }}
                  </v-progress-circular>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="12" md="3">
          <v-card class="hello4" elevation="1" min-height="100" outlined>
            <v-card-text>
              <v-row justify="center" align="center">
                <v-col cols="12" sm="6">
                  <h3>NEW EMPLOYEES</h3>

                  <div class="d-flex flex-row">
                    <v-icon color="green darken-1" large class="pt-1"
                      >mdi-plus</v-icon
                    >
                    <div class="mt-2 black--text text1">34</div>
                  </div>
                </v-col>

                <v-col cols="12" sm="6" class="text-end">
                  <v-progress-circular
                    :rotate="360"
                    :size="60"
                    :width="8"
                    :value="value"
                    color="green accent-3"
                  >
                    {{ value }}
                  </v-progress-circular>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="12" md="8">
          <v-card min-height="400" outlined elevation="1">
            <v-row>
              <v-col cols="12" md="6">
                <v-card-subtitle> Private Equity Assets </v-card-subtitle>
              </v-col>
              <v-col></v-col>
              <v-col></v-col>
              <v-col></v-col>
              <v-col>
                <v-btn
                  elevation="1"
                  color="yellow darken-2"
                  class="mt-3 ml-5"
                  small
                >
                  <div class="btn">Actions</div>
                </v-btn>
              </v-col>
            </v-row>
            <v-divider></v-divider>
            <v-img src="graph2.jpg" class="graph"></v-img>
          </v-card>
        </v-col>
        <v-col cols="12" md="4">
          <v-card min-height="400" outlined elevation="1">
            <v-row>
              <v-col>
                <v-card-subtitle> Income </v-card-subtitle>
              </v-col>
              <v-col></v-col>
              <v-col></v-col>
              <v-col></v-col>
              <v-col></v-col>
              <v-col>
                <v-icon class="mt-4 ml-6"> mdi-cog </v-icon>
              </v-col>
            </v-row>
            <v-divider></v-divider>

            <v-row>
              <v-col cols="12" class="text-right">
                <v-btn elevation="0" icon>
                  <v-icon color="black" class="mr-1"> mdi-menu </v-icon>
                </v-btn>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12" class="d-flex justify-center align-center">
                <v-progress-circular
                  :rotate="270"
                  :size="170"
                  :width="20"
                  :value="value"
                  color="blue lightened-3"
                >
                  {{ value }}
                </v-progress-circular>
              </v-col>
            </v-row>
            <v-container>
              <v-row class="mt-3">
                <v-col cols="12" md="2">
                  <div class="yellow--text text--darken-2 lb1 ml-3 mt-1">
                    32%
                  </div>
                </v-col>
                <v-col cols="12" md="10">
                  <v-progress-linear
                    v-model="valueDeterminate"
                    color="yellow accent-3"
                    class="mt-5 mr-6 ml-n6"
                  >
                  </v-progress-linear>
                </v-col>
              </v-row>
            </v-container>
            <v-row>
              <v-card-text class="ml-5 mt-n3 grey--text">
                Spendings Target
              </v-card-text>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="3">
          <v-card elevation="0" outlined min-height="100">
            <v-card-text>
              <v-row>
                <v-col col="12">
                  <h5 color="grey--text" class="new2">Income</h5>
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="12" md="6">
                  <h5 class="text1"><v-icon>mdi-currency-usd</v-icon>5,456</h5>
                </v-col>
                <v-spacing></v-spacing>
                <v-col cols="12" md="6" class="text-right">
                  <div class="new2 light-green--text ml-16">+14%</div>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="3">
          <v-card elevation="0" outlined min-height="100">
            <v-card-text>
              <v-row>
                <v-col col="12">
                  <h5 color="grey--text" class="new2">Expenses</h5>
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="12" md="6">
                  <h5 class="text1 red--text">
                    <v-icon>mdi-currency-usd</v-icon>4,764
                  </h5>
                </v-col>
                <v-spacing></v-spacing>
                <v-col cols="12" md="6" class="text-right">
                  <div class="new2 red--text ml-16">
                    <v-icon small color="red">mdi-chevron-up</v-icon>8%
                  </div>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="3">
          <v-card elevation="0" outlined min-height="100">
            <v-card-text>
              <v-row>
                <v-col col="12">
                  <h5 color="grey--text" class="new2">Spending</h5>
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="12" md="6">
                  <h5 class="text1">
                    <v-icon color="light-green">mdi-chevron-down</v-icon
                    ><v-icon>mdi-currency-usd</v-icon>1.5m
                  </h5>
                </v-col>
                <v-spacing></v-spacing>
                <v-col cols="12" md="6" class="text-right">
                  <div class="new2 light-green--text ml-16">
                    <v-icon small color="light-green">mdi-chevron-down</v-icon
                    >15%
                  </div>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="3">
          <v-card elevation="0" outlined min-height="100">
            <v-card-text>
              <v-row>
                <v-col col="12">
                  <h5 color="grey--text" class="new2">Totals</h5>
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="12" md="6">
                  <h5 class="text1"><v-icon>mdi-currency-usd</v-icon>31,564</h5>
                </v-col>
                <v-spacing></v-spacing>
                <v-col cols="12" md="6" class="text-right">
                  <div class="yellow--text new2">+76%</div>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
      <h5 class="name1 black--text my-3">Target Selection</h5>
      <v-row>
        <v-col cols="12" md="3">
          <v-card elevation="1" outlined min-height="100">
            <v-card-text class="pa-0">
              <v-row>
                <v-col cols="12" md="3">
                  <div class="phont red--text mt-3 ml-4">71%</div>
                </v-col>
                <v-col cols="12" md="9">
                
                  <v-progress-linear
                    v-model="value1"
                    color="red"
                    absolute                    
                    rounded
                    
                  >
                  </v-progress-linear>
                </v-col>
              </v-row>
              <v-row>
                <div class="new 2 grey--text ml-7 mt-2">Income Target</div>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="3">
          <v-card elevation="1" outlined min-height="100">
            <v-card-text class="pa-0">
              <v-row>
                <v-col cols="12" md="3">
                  <div class="phont green--text mt-3 ml-4">54%</div>
                </v-col>
                <v-col cols="12" md="9">
                  <v-progress-linear
                    v-model="value2"
                    color="green"
                    absolute
                    rounded
                    
                  >
                  </v-progress-linear>
                </v-col>
              </v-row>
              <v-row>
                <div class="new 2 grey--text ml-7 mt-2">Expenses Target</div>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="3">
          <v-card elevation="1" outlined min-height="100">
            <v-card-text class="pa-0">
              <v-row>
                <v-col cols="12" md="3">
                  <div class="phont yellow--text mt-3 ml-4">32%</div>
                </v-col>
                <v-col cols="12" md="9">
                  <v-progress-linear
                    v-model="value3"
                    color="yellow"
                    absolute 
                    rounded
                  >
                  </v-progress-linear>
                </v-col>
              </v-row>
              <v-row>
                <div class="new 2 grey--text ml-7 mt-2">Spendings Target</div>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="3">
          <v-card elevation="1" outlined min-height="100">
            <v-card-text class="pa-0">
              <v-row>
                <v-col cols="12" md="3">
                  <div class="phont teal--text mt-3 ml-4">89%</div>
                </v-col>
                <v-col cols="12" md="9">
                  <v-progress-linear
                    v-model="value4"
                    color="teal"
                    absolute 
                    rounded
                  >
                  </v-progress-linear>
                </v-col>
              </v-row>
              <v-row>
                <div class="new 2 grey--text ml-7 mt-2">Totals Target</div>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
        
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
export default {
  layout: "default",

  data() {
    return {
      value4: 89,
      value3: 32,
      value2: 54,
      value1: 71,
      valueDeterminate: 32,
      interval: {},
      value: 0,
      items: [
        {
          text: "Home",
          disable: false,
          href: "/",
        },
        {
          text: "Dashboards",
          disable: false,
          href: "/",
        },
        {
          text: "Mini Dashboard Example",
          disable: false,
          href: "/",
        },
      ],
    };
  },
  beforeDestroy() {
    clearInterval(this.interval);
  },
  mounted() {
    this.interval = setInterval(() => {
      if (this.value === 100) {
        return (this.value = 0);
      }
      this.value += 10;
    }, 1000);
  },
};
</script>

<style scoped>
.help {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  color: #1e88e5;
  text-align: center;
  padding-left: 5px;
  font-weight: 550;
  font-size: 10pt;
}
.style1 {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  color: black;
  font-size: 14pt;
}
.style2 {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  color: black;
  font-size: 10pt;
}
.hello1 {
  border-bottom: 5px solid rgba(58, 58, 240, 0.979);
}
.hello2 {
  border-bottom: 5px solid rgb(194, 16, 194);
}
.hello3 {
  border-bottom: 5px solid rgb(255, 217, 1);
}
.hello4 {
  border-bottom: 5px solid rgb(11, 156, 11);
}
.text1 {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 24pt;
  font-weight: 500;
}
.dog {
  margin-left: 90px;
  margin-top: -35px;
}
.graph {
  align-items: center;
  height: 340px;
}
.btn {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  text-transform: none;
  color: black;
  letter-spacing: normal;
}
.lb1 {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 16pt;
  font-weight: 700;
}
.new {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 12pt;
}
.new2 {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 14pt;
}
.name1 {
  font-size: 16pt;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}
.phont {
  font-size: 20pt;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-weight: 600;
}
</style>
