<script setup>
const recentproducts = [
  {
    brand: "Nordic EcoClean",
    name: "Eco Care Pomegranate",
    category: "Body Wash",
    href: "#",
    imageSrc: "/bodywash.png",
    score: 99,
    price: 120,

    tags: [
      {
        name: "SustainablePackaging",
      },
      {
        name: "EthicalHarvesting",
      },
    ],
  },
  {
    brand: "Clean Reserve",
    name: "Avant Garden Galbanum & Rain",
    category: "Eau De Parfum",
    href: "#",
    imageSrc: "/cleanreserve.jpg",
    score: 99,
    price: 1200,

    tags: [
      {
        name: "SustainablePackaging",
      },
      {
        name: "EthicalHarvesting",
      },
    ],
  },
  {
    brand: "Floral Street",
    name: "Sunflower Pop",
    category: "Eau De Parfum",
    href: "#",
    imageSrc: "/floralstreet.jpg",
    score: 89,
    price: 1099,

    tags: [
      {
        name: "SustainablePackaging",
      },
    ],
  },
];

const popularproducts = [
  {
    brand: "Clean Reserve",
    name: "Avant Garden Galbanum & Rain",
    category: "Eau De Parfum",
    href: "#",
    imageSrc: "/cleanreserve.jpg",
    score: 99,
    price: 1200,

    tags: [
      {
        name: "SustainablePackaging",
      },
      {
        name: "EthicalHarvesting",
      },
    ],
  },
  {
    brand: "Floral Street",
    name: "Sunflower Pop",
    category: "Eau De Parfum",
    href: "#",
    imageSrc: "/floralstreet.jpg",
    score: 89,
    price: 1099,

    tags: [
      {
        name: "SustainablePackaging",
      },
    ],
  },
  {
    brand: "Nordic EcoClean",
    name: "Eco Care Pomegranate",
    category: "Body Wash",
    href: "#",
    imageSrc: "/bodywash.png",
    score: 99,
    price: 120,

    tags: [
      {
        name: "SustainablePackaging",
      },
      {
        name: "EthicalHarvesting",
      },
    ],
  },
];

const seasonalproducts = [
  {
    brand: "Pact",
    name: "Flare Midi Party Dress",
    category: "Dresses & Skirts",
    href: "#",
    imageSrc: "/pact.jpg",
    score: 85,
    price: 120,

    tags: [
      {
        name: "SustainablePackaging",
      },
      {
        name: "EthicalHarvesting",
      },
    ],
  },
  {
    brand: "Kotn",
    name: "V-Neck Tank",
    category: "Tops",
    href: "#",
    imageSrc: "/kotn.jpg",
    score: 89,
    price: 109,

    tags: [
      {
        name: "SustainablePackaging",
      },
    ],
  },
  {
    brand: "Vetta",
    name: "The Two Piece Utility Jumpsuit",
    category: "Jumpsuits",
    href: "#",
    imageSrc: "/vetta.jpg",
    score: 89,
    price: 609,

    tags: [
      {
        name: "SustainablePackaging",
      },
    ],
  },
  {
    brand: "Quince",
    name: "European Linen Short Sleeve Shirt",
    category: "Shirts",
    href: "#",
    imageSrc: "/quince.jpg",
    score: 89,
    price: 209,

    tags: [
      {
        name: "SustainablePackaging",
      },
    ],
  },
];

const blogs = [
  {
    title: "10 Eco-friendly products to help you live a little greener",
    description:
      "Only a small percentage of our planet’s plastics are actually recycled. Buying less single-use plastic can help reduce the waste.",
    href: "/blog",
    imageUrl: "url('/ecofriendly.jpg')",
    imageAlt: "Image of a woman walking with eco-friendly shopping bag.",
    author: "Michelle Yeoh",
    authorImgSrc: "/author.jpg",
    authorImgAlt: "Image of the author",
    date: "May 12",
  },

  {
    title:
      "5 Ethical And Sustainable Clothing Brands Betting Against Fast Fashion",
    description:
      "As consumers, we’ve become increasingly conscious about our purchases, channeling the power of our vocalized objections to make a positive difference for the people involved in the making of our clothes and goods.",
    href: "/blog",
    imageUrl: "url('/sustainablefashion.jpg')",
    imageAlt: "Image of ",
    author: "Michelle Yeoh",
    authorImgSrc: "/author.jpg",
    authorImgAlt: "Image of the author",
    date: "May 10",
  },
];
</script>

<template>
  <div>
 <HomeNav/>
        
    <!-- Search bar -->
    <div
      class="w-full py-48 mb-5 bg-no-repeat bg-left lg:bg-right bg-cover bg-[url('/banner.jpg')]"
    >
      <div class="w-10/12 mx-auto space-y-3 mb-4">
        <h2 class="text-2xl font-semibold">
          <span class="text-teal-800 font-bold">Each thing</span> gathered in
          one place.
        </h2>
        <p class="text-base">
          Compare prices and value propositions on more than
          <span class="font-semibold">4.2</span> million products.
        </p>
      </div>

      <div class="w-10/12 mx-auto">
        
        <div class="lg:w-4/12">
          <Searchbar />
        </div>
      </div>
    </div>

    <!-- Recent searches section -->

    <div class="w-10/12 py-5 mx-auto">
      <h2 class="font-semibold text-2xl mb-4">Based on your recent searches</h2>
      <div class="grid grid-cols-1 lg:grid-cols-4 gap-5">
        <div v-for="recentproduct in recentproducts" :key="recentproduct.name">
          <div
            class="max-w-sm rounded-lg overflow-hidden shadow-lg hover:shadow-xl border bg-white"
          >
            <nuxt-link to="/product">
              <div class="relative w-full">
                <figure class="w-full mx-auto">
                  <img
                    class="w-full h-80 scale-75 duration-500 hover:scale-90 object-cover"
                    :src="recentproduct.imageSrc"
                    alt=""
                  />
                </figure>
                <div class="absolute top-2 right-2 flex items-center">
                  <span
                    class="bg-green-600 rounded-full px-2 py-1 font-semibold text-white cursor-help"
                    title="Eachthing Sustainability Score"
                    >{{ recentproduct.score }}</span
                  >
                </div>
              </div>

              <div class="p-5">
                <div class="space-y-2">
                  <span class="block font-bold text-xl">
                    {{ recentproduct.brand }}
                  </span>

                  <span class="block font-semibold text-lg">
                    {{ recentproduct.name }}
                  </span>

                  <span class="block text-sm">
                    {{ recentproduct.category }}
                  </span>
                </div>

                <div class="flex justify-between">
                  <div class="font-bold">{{ recentproduct.price }} kr.</div>
                  <div></div>
                  <div
                    class="flex items-center cursor-help"
                    title="230 anmeldelser"
                  >
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                  </div>
                </div>
                <div class="pt-4 flex flex-wrap">
                  <span
                    v-for="tag in recentproduct.tags"
                    class="inline-block bg-gray-200 rounded-full px-2.5 py-2 text-xs font-semibold text-gray-700 mr-2 mb-2"
                    >#{{ tag.name }}</span
                  >
                </div>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>

    <!-- Popular products section -->
    <div class="w-10/12 py-5 mx-auto">
      <h2 class="font-semibold text-2xl mb-4">Popular products</h2>
      <div class="grid grid-cols-1 lg:grid-cols-4 gap-5">
        <div
          v-for="popularproduct in popularproducts"
          :key="popularproduct.name"
        >
          <div
            class="max-w-sm rounded-lg overflow-hidden shadow-lg hover:shadow-xl border bg-white"
          >
            <nuxt-link to="/product">
              <div class="relative w-full">
                <figure class="w-full mx-auto">
                  <img
                    class="w-full h-80 scale-75 duration-500 hover:scale-90 object-cover"
                    :src="popularproduct.imageSrc"
                    alt=""
                  />
                </figure>
                <div class="absolute top-2 right-2 flex items-center">
                  <span
                    class="bg-green-600 rounded-full px-2 py-1 font-semibold text-white cursor-help"
                    title="Eachthing Sustainability Score"
                    >{{ popularproduct.score }}</span
                  >
                </div>
              </div>

              <div class="p-5">
                <div class="space-y-2">
                  <span class="block font-bold text-xl">
                    {{ popularproduct.brand }}
                  </span>

                  <span class="block font-semibold text-lg">
                    {{ popularproduct.name }}
                  </span>

                  <span class="block text-sm">
                    {{ popularproduct.category }}
                  </span>
                </div>

                <div class="flex justify-between">
                  <div class="font-bold">{{ popularproduct.price }} kr.</div>
                  <div></div>
                  <div
                    class="flex items-center cursor-help"
                    title="230 anmeldelser"
                  >
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                  </div>
                </div>
                <div class="pt-4 flex flex-wrap">
                  <span
                    v-for="tag in popularproduct.tags"
                    class="inline-block bg-gray-200 rounded-full px-2.5 py-2 text-xs font-semibold text-gray-700 mr-2 mb-2"
                    >#{{ tag.name }}</span
                  >
                </div>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>

    <!-- Blogs section -->
    <div class="w-10/12 py-5 mx-auto grid grid-cols-1 gap-8">
      <h2 class="font-semibold text-2xl mb-2">Need inspiration?</h2>
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
        <div
          v-for="blog in blogs"
          :key="blog.name"
          class="rounded-lg shadow-lg max-w-full lg:flex cursor-pointer hover:shadow-xl"
        >
          <div
            class="h-48 w-full lg:w-48 flex-none bg-cover rounded-l-lg text-center overflow-hidden"
            :title="blog.imageAlt"
            :style="{ 'background-image': blog.imageUrl }"
          ></div>

          <div class="px-5 py-3 flex flex-col justify-between space-y-5">
            <div>
              <p class="font-bold text-xl mb-2">
                {{ blog.title }}
              </p>

              <p>
                {{ blog.description }}
              </p>
            </div>

            <div class="flex items-center">
              <img
                class="w-10 h-10 rounded-full mr-2"
                :src="blog.authorImgSrc"
                :alt="blog.authorImgAlt"
              />
              <div>
                <p class="text-sm">{{ blog.author }}</p>
                <p class="text-xs">{{ blog.date }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Seasonal section -->
    <div class="w-10/12 py-5 mx-auto">
      <h2 class="font-semibold text-2xl mb-4">Summer fashion</h2>
      <div class="grid grid-cols-1 lg:grid-cols-4 gap-5">
        <div
          v-for="seasonalproduct in seasonalproducts"
          :key="seasonalproduct.name"
        >
          <div
            class="max-w-sm rounded-lg overflow-hidden shadow-lg hover:shadow-xl border"
          >
            <nuxt-link to="/product">
              <div class="relative w-full">
                <figure class="w-full mx-auto">
                  <img
                    class="w-full h-96 object-cover object-top"
                    :src="seasonalproduct.imageSrc"
                    alt=""
                  />
                </figure>
                <div class="absolute top-2 right-2 flex items-center">
                  <span
                    class="bg-green-600 rounded-full px-2 py-1 font-semibold text-white cursor-help"
                    title="Eachthing Sustainability Score"
                    >{{ seasonalproduct.score }}</span
                  >
                </div>
              </div>

              <div class="p-5">
                <div class="space-y-2">
                  <span class="block font-bold text-xl">
                    {{ seasonalproduct.brand }}
                  </span>

                  <span class="block font-semibold text-lg">
                    {{ seasonalproduct.name }}
                  </span>

                  <span class="block text-sm">
                    {{ seasonalproduct.category }}
                  </span>
                </div>

                <div class="flex justify-between">
                  <div class="font-bold">{{ seasonalproduct.price }} kr.</div>
                  <div></div>
                  <div
                    class="flex items-center cursor-help"
                    title="230 anmeldelser"
                  >
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                    <span class="material-symbols-outlined text-yellow-400">
                      star
                    </span>
                  </div>
                </div>
                <div class="pt-4 flex flex-wrap">
                  <span
                    v-for="tag in seasonalproduct.tags"
                    class="inline-block bg-gray-200 rounded-full px-2.5 py-2 text-xs font-semibold text-gray-700 mr-2 mb-2"
                    >#{{ tag.name }}</span
                  >
                </div>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>

    <!-- Labels and certs section -->
  </div>
</template>

<style scoped>
.cls-1 {
  fill: green;
}
</style>
