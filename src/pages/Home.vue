<template>
  <!--Header---------->
  <div class="">
    <div class="headerGradient">
      <div class="row pageWidth header q-px-sm">
        <div class="col-12 col-md-6">
          <div class="headerText text-h1 font fadeInUp">
            Simplify<br>Your<br>Backups
          </div>
          <div class="headerSubText q-pt-lg fadeInUp">
            Consolidate your information and save on operational costs
          </div>
          <div class="q-py-xl">
            <q-btn label="Get Started" no-caps class="blueButton text-white" @click="addMSP = true" />
            <q-dialog v-model="addMSP">
              <AddMSP></AddMSP>
            </q-dialog>
          </div>
        </div>
        
        <div class="col-12 col-md-6">
          <div class="largeScreen q-py-xl">
            <img src='~/assets/clouddata.png' style="width:100%; z-index:-1" class="fadeInUpDelay1"/>
          </div>
        </div>
      </div>
    </div>
    
    <div class="pageWidth">
      <h1 class="text-h1 headerText">
        Some<br>Homepage<br>Text
      </h1>
      <div class="headerSubText">
        Some subtitle text to describe some other stuff
      </div>

      <h1 class="text-h1 headerText">
        Some<br>Homepage<br>Text
      </h1>
      <div class="headerSubText">
        Some subtitle text to describe some other stuff
      </div>
    </div>
    
    
  </div>
  
</template>

<script>
import AddMSP from 'components/AddMSP.vue';

export default {
  data() {
    return {
      addMSP: false
    }
  },
  components: {AddMSP}
}
</script>
