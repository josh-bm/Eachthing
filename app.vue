<script setup>
import '@/assets/css/tailwind.css'
import "/app.css"

useHead({
  title: 'Eachthing',
  viewport: 'width=device-width, initial-scale=1, maximum-scale=1',
  charset: 'utf-8',
  meta: [
    { name: 'description', content: 'Eachthing is a price comparison website that focuses on transparency and working with brands that have certifications in regards to sustainability and eco-friendliness.' }
  ],
})

</script>

<template>
  <div class="bg-gray-50">
      <Head>
        <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
      
      </Head>
      <div>
    <NuxtPage></NuxtPage>
    </div>

      <Footer />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
</style>