<script setup>
const categories = [
  {
    name: "Parfumer",
    href: "#",
    imageSrc: "/perfume.jpg",
    subcategories: [
      {
        name: "Eau de Toilette",
      },
      {
        name: "Eau de Parfum",
      },
      {
        name: "Gift Boxes",
      },
      {
        name: "Perfum",
      },
      {
        name: "Eau de Cologne",
      },
      {
        name: "Eau Fraiche",
      },
      {
        name: "Body Mist",
      },
    ],
  },
  {
    name: "Makeup",
    href: "#",
    imageSrc: "/makeup.jpg",
    subcategories: [
      {
        name: "Base Makeup",
      },
      {
        name: "Lash Products",
      },
      {
        name: "Lipsticks",
      },
      {
        name: "Eyeshadows",
      },
      {
        name: "Cosmetic Tools",
      },
      {
        name: "Eyebrow Products",
      },
      {
        name: "Gift Boxes, Sets & Multi-Products",
      },
    ],
  },
  {
    name: "Nail Products",
    href: "#",
    imageSrc: "/nail.jpg",
    subcategories: [
      {
        name: "Nail Polishes",
      },
      {
        name: "False Nails",
      },
      {
        name: "Nail Tools",
      },
      {
        name: "Nail Polish Removers",
      },
      {
        name: "Nail Art",
      },
    ],
  },
];

const products = [
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
    brand: "Le Labo",
    name: "Santal 33",
    category: "Eau De Parfum",
    href: "#",
    imageSrc: "/santal33.png",
    score: 89,
    price: 1099,

    tags: [
      {
        name: "SustainablePackaging",
      },
    ],
  },

  {
    brand: "The Nuew Co",
    name: "Forest Lungs",
    category: "Eau de Parfum",
    href: "#",
    imageSrc: "/forestlungs.jpg",
    score: 89,
    price: 1099,

    tags: [
      {
        name: "SustainablePackaging",
      },
    ],
  },
];
</script>

<template>
  <div>
    <Navbar />

    <div>
      <div class="w-10/12 mx-auto p-5 ">
        <h2 class="font-semibold text-4xl mb-12 lg:mb-4 text-center">
          Search results for "Bodywash"
        </h2>

        <h2 class="font-semibold text-2xl mb-4">Categories</h2>

        <div
          class="grid grid-cols-1 lg:grid-cols-4 space-y-8 lg:space-x-8 lg:space-y-0"
        >
          <a
            v-for="category in categories"
            :key="category.name"
            href="/categories/beauty"
            class="relative w-full h-40 rounded-lg p-6 flex flex-col overflow-hidden hover:opacity-75 xl:w-auto"
          >
            <span aria-hidden="true" class="absolute inset-0">
              <img
                :src="category.imageSrc"
                alt=""
                class="w-full h-full object-center object-cover"
              />
            </span>
            <span
              aria-hidden="true"
              class="absolute inset-x-0 bottom-0 h-2/3 bg-gradient-to-t from-gray-800 opacity-50"
            />
            <span
              class="relative mt-auto text-center text-xl font-bold text-white"
              >{{ category.name }}</span
            >
          </a>
        </div>

        <!-- Popular products -->
        <div class="w-full mt-12 border-t py-10">
          <h2 class="font-semibold text-2xl mb-4">Products (21)</h2>
          <div class="grid grid-cols-1 lg:grid-cols-4 gap-5">
            <div v-for="product in products" :key="product.name">
              <div
                class="max-w-sm rounded-lg overflow-hidden shadow-lg hover:shadow-xl px-5 py-3 border bg-white"
              >
                <nuxt-link to="/product">
                  <div class="relative w-full">
                    <figure class="w-8/12 mx-auto">
                      <img
                        class="w-full h-72 scale-90 duration-500 hover:scale-100 object-cover"
                        :src="product.imageSrc"
                        alt=""
                      />
                    </figure>
                    <div class="absolute top-0 right-0 flex items-center">
                      <span
                        class="bg-green-600 rounded-full px-3 py-1 font-semibold text-white cursor-help"
                        title="Eachthing Sustainability Score"
                        >{{ product.score }}</span
                      >
                    </div>
                  </div>

                  <div class="py-4 space-y-2">
                    <span class="block font-bold text-xl">
                      {{ product.brand }}
                    </span>

                    <span class="block font-semibold text-lg">
                      {{ product.name }}
                    </span>

                    <span class="block text-sm">
                      {{ product.category }}
                    </span>
                  </div>

                  <div class="flex justify-between">
                    <div class="font-bold">{{ product.price }} kr.</div>
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
                      v-for="tag in product.tags"
                      class="inline-block bg-gray-200 rounded-full px-2.5 py-2 text-xs font-semibold text-gray-700 mr-2 mb-2"
                      >#{{ tag.name }}</span
                    >
                  </div>
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
