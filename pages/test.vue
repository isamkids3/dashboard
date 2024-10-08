<template>
  <v-row>
    <v-col cols="12">
      <v-row>
        <v-col cols="12">
          <h1>Car Management System</h1>
        </v-col>
      </v-row>
      <v-row class="d-flex justify-center align-center" min-height="400">
        <v-col cols="12" class="text--black">
          <v-card height="590" class="mb-6">
            <v-data-table :headers="headers" :items="responseData">
            </v-data-table>
          </v-card>
          <v-row>
            <v-col cols="12">
              <v-dialog v-model="dialog" width="800">
                <template v-slot:activator="{ on, attrs }">
                  <v-btn v-bind="attrs" v-on="on" class = "btn mr-1"> Create </v-btn>
                </template>

                <v-card>
                  <v-card-title class="text-h5 grey lighten-2">
                    Add New Vehicle
                  </v-card-title>

                  <v-card-text>
                    <v-text-field
                      v-for="(field, label) in fields"
                      :key="label"
                      :label="field.title"
                      :rules="field.rule"
                      
                      
                      v-model="fieldValues[label]"
                    >
                    </v-text-field>
                  </v-card-text>

                  <v-divider></v-divider>

                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <form>
                      <v-btn color="primary" text @click="submitData">
                        Submit
                      </v-btn>
                    </form>
                  </v-card-actions>
                </v-card>
              </v-dialog>
              <v-dialog v-model="dialog2" width="800">
                <template v-slot:activator="{ on, attrs }">
                  <v-btn v-bind="attrs" v-on="on" class = "btn mx-1"> Edit</v-btn>
                </template>

                <v-card>
                  <v-card-title class="text-h5 grey lighten-2">
                    Edit
                  </v-card-title>

                  <v-card-text>
                    <v-text-field
                    label = "ID"
                    v-model="fieldValues.id"
                    :rules="edit.required">
                    

                      </v-text-field>
                    <v-text-field
                      v-for="(field, label) in fields"
                      :key="label"
                      :label="[field.title]"
                      v-model="fieldValues[label]"
                    >
                    </v-text-field>
                  </v-card-text>

                  <v-divider></v-divider>

                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <form>
                      <v-btn color="primary" text @click="editData">
                        Submit
                      </v-btn>
                    </form>
                  </v-card-actions>
                </v-card>
              </v-dialog>
              <v-dialog v-model="dialog3" width = "800">
                <template v-slot:activator="{ on, attrs }">
                  <v-btn v-bind="attrs" v-on="on" class = "btn mx-1"> Delete</v-btn>
                </template>

                <v-card>
                  <v-card-title class="text-h5 grey lighten-2">
                    Delete
                  </v-card-title>

                  <v-card-text>
                    <v-text-field
                    label = "ID"
                    v-model="fieldValues2.id"
                    :rules = "edit.required">
                    
                      </v-text-field>
                    
                   
                  </v-card-text>

                  <v-divider></v-divider>

                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <form>
                      <v-btn color="primary" text @click="deleteData">
                        Submit
                      </v-btn>
                    </form>
                  </v-card-actions>
                </v-card>
              </v-dialog>
              <v-dialog
              v-model = "errorDialog"
              width = "600">
                <v-card
                >
                  <v-row >
                    <v-col cols = "12" align = "center" class = "mt-5">
                      <v-img src = "err1.png" style = "height:80px; width:80px; " >
                      </v-img>
                    </v-col>
                  </v-row>
                  <v-row>
                    <v-col cols = "12">
                      <v-card-text align = "center" class = "text mt-n6"> 
                        Error has occured! Make sure data entered is correct.
                      </v-card-text>
                    </v-col>
                  </v-row>
                </v-card>
              </v-dialog>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<style>
.btn {
  letter-spacing: normal;
  text-transform: none;
  font-weight: normal;
}
.picture{
  height: 90px;
  width: 90px;
}
.text{
  font-size: 18pt;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

</style>

<script>
import axios from "axios";

export default {
  layout: "default",
  data() {
    return {
      dialog: false,
      dialog2: false,
      dialog3: false,
      errorDialog: false,
      responseData: [],
      edit: {
        required: [value => !!value || 'Required.']
      },
      headers: [
        { text: "ID", value: "id" },
        { text: "Number Plate", value: "number_plate",  },
        { text: "Car Brand", value: "car_brand", },
        { text: "Car Color", value: "car_color", },
        { text: "Full Name", value: "owner_full_name",  },
        { text: "Insured", value: "insured", },
      ],

      fields: [
        { label: "number_plate",  title: "Number Plate",rule: [value => !!value || 'Required.'], },
        { label: "car_brand", title: "Car Brand",rule: [value => !!value || 'Required.']   },
        { label: "car_color", title: "Car Color",rule: [value => !!value || 'Required.']   },
        { label: "owner_full_name", title: "Full Name",rule: [value => !!value || 'Required.'] },
        { label: "insured", title: "Insured",rule: [value => !!value || 'Required.']  },
      ],
      fieldValues: {
        id: "", // Initialize ID field value
        number_plate: "",
        car_brand: "",
        car_color: "",
        owner_full_name: "",
        insured: "",
      },
      fieldValues2: {
        id: ""
      }
    };
  },

  created() {
    this.getData();
  },

  methods: {
    async getData() {
      try {
        const response = await axios.get("http://127.0.0.1:8000/api/cars");
        if (response.data && Array.isArray(response.data.data)) {
          // Assuming response.data.data contains the array of objects
          this.responseData = response.data.data;
        } else {
          this.errorDialog = true;
          console.error("Invalid response format:", response.data);
        }
      } catch (error) {
        this.errorDialog = true;
        console.error("Error fetching data:", error);
      }
    },

    async submitData() {
      try {
        // prepare data in the fields to be sent
        const dataToSend = {};
        this.fields.forEach((field, label) => {
          dataToSend[field.label] = this.fieldValues[label];
        });

        // Send POST request to the server
        const response = await axios.post(
          "http://127.0.0.1:8000/api/cars",
          dataToSend
        );

        // Success reponse
        console.log("Data submitted successfully:", response.data);

        //Close dialog
        this.dialog = false;
        location.reload();
      } catch (error) {
        this.errorDialog = true;
        console.error("Error submitting data:", error);
      }
    },
    async editData() {
      try {
        const dataToSend = {};
        this.fields.forEach((field, label) => {
          dataToSend[field.label] = this.fieldValues[label];
        });

        // Assuming the ID is part of the URL
        const response = await axios.patch(
          `http://127.0.0.1:8000/api/cars/${this.fieldValues.id}`, // Use the ID from fieldValues
          dataToSend
        );

        console.log("Data edited successfully:", response.data);

        this.dialog2 = false; // Close the edit dialog
        location.reload();
      } catch (error) {
        this.errorDialog = true;
        console.error("Error editing data:", error);
      }
    },
    async deleteData() {
      try {

        //Prepares data to be sent
        const dataToSend = {};
        this.fields.forEach((field, id) => {
          dataToSend[field.id] = this.fieldValues2.id;
        });
        


        // Assuming the ID is part of the URL
        const response = await axios.delete(
          `http://127.0.0.1:8000/api/cars/${this.fieldValues2.id}`, // Use the ID from fieldValues2
          dataToSend
        );

        console.log("Data deleted successfully:", response.data);

        this.dialog3 = false; // Close the edit dialog
        location.reload();
      } catch (error) {
        this.errorDialog = true;
        console.error("Error deleting data:", error);
      }
    },

    

    
  },
};
</script>
