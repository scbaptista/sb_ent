<template>
  <v-card style="height:100%;">
    <v-card-title class="titleCustom">Execute</v-card-title>
    <v-card-subtitle class="subtitleCustom">Configure Module</v-card-subtitle>

    <v-card-text>
      <v-form>
        <v-row>
          <v-col cols="5" class="ma-1">
            <div class="labelBold">
              Name
              <span @mouseover="hover = true" @mouseleave="hover = false">
                <v-icon class="infoIcon">info_outline</v-icon>
              </span>
              <span class="hoverText" v-if="hover">Message.</span>
            </div>
          </v-col>
          <v-col class="ma-1">
            <v-text-field
              class="selectBox"
              v-model="nameParam"
              placeholder="Run optimization"
              required
              solo
            />
          </v-col>
        </v-row>

        <v-row class="mt-n9">
          <v-col cols="5" class="ma-1">
            <div class="labelBold">
              Asset tag
              <span @mouseover="hover2 = true" @mouseleave="hover2 = false">
                <v-icon class="infoIcon">info_outline</v-icon>
              </span>
              <span class="hoverText" v-if="hover2">Message</span>
            </div>
          </v-col>
          <v-col class="ma-1 ">
            <v-text-field
              class="selectBox"
              v-model="assetParam"
              placeholder="run_optimization"
              required
              solo
            />
          </v-col>
        </v-row>

        <v-row class="mt-n9">
          <v-col cols="10" class="ma-1">
            <div class="labelBold font-weight-bold">Upload</div>
            <v-file-input
              multiple
              label="File input"
              prepend-icon="cloud_upload"
            >
            </v-file-input>
          </v-col>
        </v-row>

        <v-tabs
          background-color="transparent"
          color="#022f40"
          slider-color="#1771f8"
        >
          <v-tab class="labelBold">Inputs</v-tab>
          <v-tab class="labelBold">Outputs</v-tab>
        </v-tabs>

        <v-row>
          <v-col class="text-right">
            <v-btn style="border: 1px dashed" right class="button" outlined>
              <v-icon class="mr-2">add_circle</v-icon>
              Add input
            </v-btn>
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="5,5" class="ma-1">
            <div class="labelNormal">Assets</div>
            <v-select
              class="pt-2 selectBox"
              :items="items"
              append-icon="keyboard_arrow_down"
              label="Select asset"
              solo
            ></v-select>
          </v-col>

          <v-col cols="5,5" class="ma-1">
            <div class="labelNormal">Argument name</div>
            <v-text-field
              class="pt-2 selectBoxOpac"
              v-model="argName"
              label="--params"
              required
              solo
            />
          </v-col>
        </v-row>
      </v-form>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    nameParam: "",
    assetParam: "",
    argName: "",
    items: ["Item1", "Item2"],
    hover: false,
    hover2: false,
    hover3: false
  })
};
</script>

<style scoped>
.titleCustom {
  font-family: "Open Sans";
  font-stretch: normal;
  font-size: 22px !important;
  font-weight: 600;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  color: #022f40;
}
.subtitleCustom {
  font-family: "Open Sans";
  font-size: 18px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  color: #4d4f5c !important;
  padding-top: 10px;
}
.labelBold {
  text-transform: none;
  color: #022f40;
  font-size: 16px;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  font-weight: 500;
  padding-top: 10px;
}
.labelNormal {
  color: #4d4f5c;
  font-size: 15px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  padding-top: 10px;
}
.infoIcon {
  color: #07d2bf;
  border-radius: solid 1px;
  background-color: #fcfcfc;
}
.selectBox {
  border-radius: 4px;
  background-color: #ffffff;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  -webkit-text-fill-color: #4d4f5c;
  font-size: 15px;
}
.selectBoxOpac {
  border-radius: 4px;
  background-color: #ffffff;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  -webkit-text-fill-color: #e0e0e0;
  font-size: 15px;
}
.button {
  color: #07d2bf;
  text-transform: none; /* para não ficar em caps lock  */
  border-radius: 4px;
  font-size: 14px;
  font-family: "Open Sans";
  padding-top: 10px;
  font-weight: normal;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  background-color: #ffffff;
}
.hoverText {
  color: #4d4f5c;
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  padding-top: 10px;
}
</style>
