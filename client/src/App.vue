<template>
  <div class="flex flex-col bg-[#FCFCFC] pb-10 h-screen">

    <!-- Page title starts -->
    <div class="flex bg-[#576CA8] pt-8 pb-16 relative z-10 justify-center items-center">
      <div class="container px-6 mx-auto flex flex-col lg:flex-row items-start lg:items-center justify-between">

        <div class="ml-0 lg:ml-20 my-6 lg:my-0">
          <h4 class="text-2xl font-semibold text-white mb-2">Profile Picture Generator</h4>

        </div>
      </div>
    </div>
    <!-- Page title ends -->

    <div class="flex flex-col justify-center items-center">

      <div class="flex justify-center rounded-xl shadow-xl relative bg-[#FCFAFA] z-10 -mt-8 mb-8 p-5 w-4/5 lg:w-1/3">

        <form action="" @submit.prevent="inputName">



          <input v-model="text" type="text" id="first_name"
            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
            placeholder="Masukan nama kamu..." required>


          <div class="flex items-center justify-center flex row">
            <button type="submit" class="bg-[#E98A15] p-2 lg:p-3 text-white rounded-xl mt-4 hover:bg-[#EEA144]">
              Buat profile baru
            </button>
          </div>

          <div v-if="roboAddress" class="flex justify-center p-5 mt-5">

            <img class="rounded-full h-48 lg:h-72 w-48 lg:w-72 shadow-xl" :src="roboAddress" alt="">


          </div>


        </form>

      </div>




    </div>
  </div>
</template>

<script>
export default {
  name: "",
  data() {
    return {
      text: "",
      roboAddress: "",
    };
  },
  methods: {
    inputName() {
      this.roboAddress = `https://robohash.org/${this.text}.png`;
      this.text = "";
    },
  },

};
</script>
