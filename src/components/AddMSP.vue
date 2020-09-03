<template>
    <div>
      <q-carousel
        v-model="slide"
        transition-next="scale"
        animated
        control-color="black"
        navigation
        class="white text-black shadow-1 rounded-borders mspForm"
      >
        <q-carousel-slide :name="1" class="col">
            <div class="text-center">
                <div class="text-h4">
                {{ formHeader }}
                </div>
                <div class="q-my-xl">
                    Select a Managed Service Provider from the dropdown below.
                </div>
                
            </div>

            <div class="q-mt-md text-center">
                <q-select color="purple-8" filled v-model="mspSelected" :options="mspOptions" label="Managed Service Provider">
                </q-select>

                <div class="q-pt-xl">
                    <q-btn color="purple" no-caps icon-right="keyboard_arrow_right" v-if="mspSelected" @click="slide++">Next</q-btn>
                </div>
            </div>
        </q-carousel-slide>

        <q-carousel-slide :name="2" class="col">
            <div class="text-center">
                <div class="text-h4">
                {{ formHeader }}
                </div>
                <div class="q-my-xl">
                    Enter in your credentials.
                </div>
            </div>

            <div class="text-center">
                <q-input filled v-model="username" label="Username" class="q-pb-sm"/>
                <q-input v-model="password" filled :type="isPwd ? 'password' : 'text'" label="Password">
                    <template v-slot:append>
                    <q-icon
                        :name="isPwd ? 'visibility_off' : 'visibility'"
                        class="cursor-pointer"
                        @click="isPwd = !isPwd"
                    />
                    </template>
                </q-input>

                <div class="q-pt-xl">
                    <q-btn color="purple" no-caps icon-right="keyboard_arrow_right" @click="slide++">Next</q-btn>
                </div>
            </div>
        </q-carousel-slide>

        <q-carousel-slide :name="3" class="col">
            <div class="text-center">
                <div class="text-h4">
                {{ formHeader }}
                </div>
                <svg class="checkmark" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 52 52"><circle class="checkmark__circle" cx="26" cy="26" r="25" fill="none"/><path class="checkmark__check" fill="none" d="M14.1 27.2l7.1 7.2 16.7-16.8"/></svg>
                
                <div class="q-mt-md">
                    {{ mspSelected }} has been added to your dashboard!
                </div>
            </div>

            <div class="q-pt-xl text-center">
                    <q-btn color="purple" no-caps v-close-popup>Done</q-btn>
                </div>
        </q-carousel-slide>
      </q-carousel>
    </div>
</template>

<script>
export default {
  data() {
    return {
      getStarted: false,
      formHeader: 'Add a Managed Service Provider',
      slide: 1,
      lorem: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Natus, ratione eum minus fuga, quasi dicta facilis corporis magnam, suscipit at quo nostrum!',
      mspOptions: ['Microsoft Azure', 'Amazon AWS', 'Google Cloud Platform'],
      mspSelected: '',
      username: '',
      password: '',
      isPwd: true
    }
  }
}
</script>

<style lang="scss">
.mspForm {
    height:500px;
    max-width:500px;
    position:relative;
}
</style>