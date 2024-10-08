<template>
<v-row justify  = "center">
  
  <v-col cols ="12" sm = "8">
    <v-card class = "text-center">
      <v-row no-gutters>
        <v-col cols = "12" sm = "8" class= "d-flex justify-center align-center">
          
          <v-img src ="bg2.jpg" height = "650">
            <v-card-title class="text-h2" 
            ><div class= "stylefortitle">Welcome to the website</div></v-card-title>
            <div class = "text-h5"><div class = "styleforsubtitle">Lorem ipsum dolor sit amet. Qui mollitia dolorem aut recusandae quia eos inventore omnis. Ut voluptas Quis quo quaerat laborum sed accusamus aliquid sit ullam galisum sit quisquam voluptatum ut doloremque autem qui tenetur laborum. Ut galisum labore et nemo accusantium non magni dolore aut rerum tempore sit dolores obcaecati ea rerum nihil?</div>
         </div>
            </v-img>
          
        </v-col>
        <v-col cols = "12" sm = "4">
          <v-card-title class="styleforlogin ml-16">
           Login
           
          </v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field
          
            label="Username"
            prepend-icon = "mdi-account"
            dense
            filled
            >
            
            </v-text-field>
            <v-text-field
            label = "Password"
            prepend-icon = "mdi-key"
            dense 
            rounded
            filled>

            </v-text-field>
          </v-form>
        </v-card-text>
        <v-row class = "justify-center align-center">
          <v-col cols = 12>
            <v-btn
            rounded
            elevation = 0
            class = "logbtn mt-n5"
            to = "dashboard"
            color = "grey lighten-2">
            LOG IN

            </v-btn>
          </v-col>
        </v-row>
          <v-checkbox
          style= "padding-left: 15px; padding-top: 0px;"
          v-model = "hover"
          label = "Remember Me"
          ></v-checkbox>
        
           <a href="https://www.instagram.com/accounts/password/reset/"><span class ="underlined-text">Forgot Password?</span></a>
         
        </v-col>      
      </v-row>
     </v-card>
      
  </v-col>
</v-row>
    </template>
       

<script>
export default {
  layout: 'loginlayoiut'
}
</script>
<style scoped>
.underlined-text {
  text-decoration: underline;
  text-align: right;
}
.stylefortitle {
  color: white;
  text-align: left;
  text-align: justify;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  padding: 64px;
  font-weight: 400;
}
.styleforsubtitle{
  color: white;
  text-align: left;
  text-align: justify;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  padding-left: 64px;
  padding-right: 64px;
  padding-bottom: 64 px;
  padding-top: 0px;
  font-weight: 400;
}
.styleforlogin{
  font-weight:350 ;
  font-size: 32pt;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  padding-top: 150px;
  padding-bottom: 30px;
  text-align: justify;

  


}
.style2{
  padding-left: 50px;
  padding-right: 50px;

}
.logbtn{
  text-transform: none;
  letter-spacing: normal;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

</style>