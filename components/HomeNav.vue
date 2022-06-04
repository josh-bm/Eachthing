<script>
import Modal from './Modal.vue'

export default {
  components: {
    Modal
  },
  data() {
    return {
      showModal: false
    }
  }
}
</script>

<template>
  <div>
   <header>
      <nav class="w-10/12 py-5 mx-auto grid grid-cols-2 items-center">

        <div class="flex items-center space-x-7">
          <nuxt-link to="/" class="cursor-pointer">
            <figure class="w-10">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 363.78 363.78"
              >
                <defs></defs>
                <title>eachthing</title>
                <path
                  class=""
                  d="M194.51,17.56c-100.29,0-181.89,81.6-181.89,181.89s81.6,181.89,181.89,181.89,181.89-81.6,181.89-181.89S294.8,17.56,194.51,17.56ZM303.6,230.08c-22.85,55.9-68.89,81.6-109.16,81.6a89,89,0,0,1-19.78-2.15c-30.94-7-62.69-32.74-66.29-83.71a9.11,9.11,0,0,0-7.78-8.38h0c-18.69-2.68-31.54-5.6-32.35-5.77a13.46,13.46,0,0,1-10-16.05,13.09,13.09,0,0,1,15.7-10.14,418,418,0,0,0,46.43,7.46c.14,0,.25,0,.39,0a14.11,14.11,0,0,1,1.76.25c38.44,3.8,84.59,3.06,104.41-15.81,8.13-7.78,10.95-18.09,8.8-32.49-3.63-20.87-22.81-29.57-38.12-30.66-21.61-1.51-51,9.86-62.55,47a13.1,13.1,0,0,1-16.54,8.7,13.51,13.51,0,0,1-8.52-16.9c15.17-48.58,55.83-67.9,89.41-65.51,15.07,1.06,28.83,6.2,39.78,14.89a60.9,60.9,0,0,1,22.49,38.09.6.6,0,0,0,0,.25c4.4,29.11-6.72,46.68-16.83,56.32-16.16,15.38-42.81,23.66-79.49,24.68-2.92.11-7.29.07-11.83,0-2.5,0-7.11-.32-12.57-.7a6.43,6.43,0,0,0-6.86,7c3.49,30.1,19.92,50.83,46.15,56.78,33.41,7.6,78.47-12,99.8-64.28a12.7,12.7,0,1,1,23.51,9.61ZM144.27,164.21c3-23.66,26.93-45.59,61.67-41.47a5.2,5.2,0,0,1,4.61,4.61A5.08,5.08,0,0,1,205,133c-31.65-3.84-48.72,16.76-50.76,32.63a5,5,0,0,1-5.32,4.44,1.32,1.32,0,0,1-.35,0A5.12,5.12,0,0,1,144.27,164.21Z"
                  transform="translate(-12.62 -17.56)"
                ></path>
              </svg>
            </figure>
          </nuxt-link>
          <ul class="space-x-5 font-medium text-lg ">

           <nuxt-link to="/categories" class="hover:text-teal-800"> Categories </nuxt-link>

            <nuxt-link to="/blogs" class="hover:text-teal-800"> Guides </nuxt-link>

             <nuxt-link to="/about" class="hover:text-teal-800"> About us </nuxt-link>
             </ul>



        </div>



        <div>
          <ul class="flex items-center justify-end space-x-5">
           
            <nuxt-link to="/signup" class="text-lg font-medium hover:text-teal-800">Log in</nuxt-link>

            <nuxt-link to="/signup" class="">
              <button
                type="button"
                class="button bg-teal-800 hover:bg-teal-900 text-white p-3 rounded-lg shadow-lg"
              >
                Sign up
              </button>
            </nuxt-link>
          </ul>
        </div>
      </nav>
    </header>

    <!-- <button type="button" data-toggle="modal" data-target="#myModal">Open Modal</button> -->
  </div>
</template>
