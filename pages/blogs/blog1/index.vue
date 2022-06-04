<script setup>
const articles = [
  {
    title: "Spaghetti Scrubs",
    description:"The Spaghetti Scrub cookware scrubbers work astonishingly well, and are much less wasteful than having to throw away a cheap plastic scrubbing wand every few weeks. It's comprised of cotton strips and pulverized, dried corn cobs, giving its noodle-like strands a coarse — but not too rough — texture.",
    imageUrl:"/scrubs.jpg",
    },

      {
    title: "Silicone Stretch Lids",
    description:"Instead of awkwardly covering opened, half-used cans of ingredients, bowls of leftovers, and cut fruit with plastic wrap, these stretchy silicone lids will help make everything look a lot more appetizing.",
    imageUrl:"/lids.jpg",
    },

    
      {
    title: "Clean Essentials Kit",
    description:"Since most cleaning products are comprised mostly of water, it seems silly to pay extra for something that comes out of your faucet. That's just one of the many reasons we love Blueland.",
    imageUrl:"/kit.jpg",
    },

    
      {
    title: "Dish Washing Block Soap",
    description:"Bar soap is nothing new, but this might be the first dishwashing bar soap we've ever come across. Wet the No Tox Life Vegan Dish Block onto your sponge, and then work it up into a lather to scrub down your dishes, silverware, glasses, and pots as you would normally. It provides the same fresh clean without the plastic packaging or mystery ingredients.",
    imageUrl:"/soap.jpg",
    },

    
      {
    title: "Silicone Reusable Food Storage Bag",
    description:"Your plastic food-storage bag use stops here. Available in a variety of sizes, these silicone Stasher bags are great for packing up sandwiches and snacks on the go.",
    imageUrl:"/bag.jpg",
    },
    ]
</script>

<template>
  <div>
    <Navbar />

    <div class="w-10/12 mx-auto py-5 space-y-5">
      <section class="w-1/2 text-center w-full mx-auto space-y-5">
        <p class="text-gray-400">Published January 13, 2021</p>
        <h2 class="font-bold text-3xl mb-3">
          5 ECO-FRIENDLY PRODUCTS TO HELP YOU LIVE A LITTLE GREENER IN 2022
        </h2>
        <p>
          Only a small percentage of our planet’s plastics are actually
          recycled. Buying less single-use plastic can help reduce the waste.
        </p>
      </section>

      <section class="w-2/3 mx-auto space-y-5">
        <figure class="">
          <img class="w-full" src="/ecofriendly.jpg" alt="" />
        </figure>
        <p>
        It's no exaggeration to say that our single-use plastic consumption has gotten out of control. According to the EPA, in 2018, 27 million tons of plastic were landfilled, while only 3 million tons were recycled. And this does not account for the staggering amounts of unprocessed litter on land and in our waterways and oceans.
        </p>
        <p>
          It's difficult to grapple with one's own impact on the environment. Although small changes can seem futile in the face of the millions of tons of single-use plastic thrown away each year, change has to start on an individual level. Thinking about the disposable products that we use in our everyday lives can help us make better choices as consumers.
        </p>
        <p>
          The 5 eco-friendly products in this guide can help you replace throwaway items that would otherwise remain buried on our planet for hundreds of years ... if not longer. Our team has also been able to test and live with a significant number of these products to evaluate their ease of use for months (or even years), and we've denoted our favorite eco-friendly standouts below.
        </p>
        <p>
          Buying smarter is by no means the only way to make a difference, but it's a good first step to take. Plus, who knows? Becoming more aware of your single-use waste today could help you plan everything from your meals to your travel more intentionally in the future. These are the best eco-friendly products if you're ready to start making the switch.
        </p>
      </section>

      <section class="w-2/3 mx-auto space-y-5 mt-5"  v-for="article in articles" :key="article.name">
        <nuxt-link to="/product">
        <figure class="flex">
          <img class="w-4/12" :src="article.imageUrl" alt="" />
          <div class="px-5">
             <h3 class="font-bold text-xl mb-3">{{ article.title }}</h3>
        <p>
          {{ article.description }}
        </p>
          </div>
        </figure>
       </nuxt-link>
      </section>


    </div>
  </div>
</template>
