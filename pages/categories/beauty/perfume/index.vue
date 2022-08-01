<script setup>
import { ref } from "vue";
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/vue";

const sortOptions = [
  { name: "Most Popular", href: "#", current: true },
  { name: "Best Rating", href: "#", current: false },
  { name: "Newest", href: "#", current: false },
];

const filters = [
  {
    id: "color",
    name: "Color",
    options: [
      { value: "white", label: "White" },
      { value: "beige", label: "Beige" },
      { value: "blue", label: "Blue" },
      { value: "brown", label: "Brown" },
      { value: "green", label: "Green" },
      { value: "purple", label: "Purple" },
    ],
  },
  {
    id: "category",
    name: "Category",
    options: [
      { value: "new-arrivals", label: "All New Arrivals" },
      { value: "eau-de-parfum", label: "Eau De Parfum" },
    ],
  },
];

const mobileFiltersOpen = ref(false);

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
    name: "Avant Garden Galbanum",
    category: "Eau De Parfum",
    href: "#",
    imageSrc: "/cleanreserve.jpg",
    score: 99,
    price: 1200,

    tags: [
      {
        name: "SustainablePackaging",
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

const pages = [
  { name: "Beauty", href: "#", current: false },
  { name: "Perfume", href: "#", current: true },
];
</script>

<template>
  <div>
    <Navbar />

    <div>
      <div class="w-10/12 mx-auto p-5">
        <!-- Breadcrumbs -->
        <nav class="flex mb-5" aria-label="Breadcrumb">
          <ol role="list" class="flex items-center space-x-4">
            <li>
              <div>
                <a
                  href="#"
                  class="text-sm font-medium text-gray-500 hover:text-gray-700"
                >
                  <span>Home</span>
                </a>
              </div>
            </li>
            <li v-for="page in pages" :key="page.name">
              <div class="flex items-center">
                <span
                  class="material-symbols-outlined flex-shrink-0 h-5 w-5 text-gray-400"
                >
                  chevron_right
                </span>

                <a
                  :href="page.href"
                  class="ml-4 text-sm font-medium text-gray-500 hover:text-gray-700"
                  :aria-current="page.current ? 'page' : undefined"
                  >{{ page.name }}</a
                >
              </div>
            </li>
          </ol>
        </nav>

        <h2 class="font-semibold text-4xl mb-4 text-center">Perfume</h2>

        <div class="flex relative">
          <!-- Filter -->
          <div class="w-3/12">
            <h2 class="sr-only">Filters</h2>

            <button
              type="button"
              class="inline-flex items-center lg:hidden"
              @click="mobileFiltersOpen = true"
            >
              <span class="text-sm font-medium text-gray-700">Filters</span>
            </button>

            <div class="hidden lg:block">
              <form class="divide-y divide-gray-200 space-y-10 pr-10">
                <div>
                  <fieldset>
                    <legend class="block text-sm font-medium text-gray-900">
                      Price
                    </legend>

                    <div class="pt-6 space-y-2">
                      <input type="range" class="w-full" />

                      <div class="grid grid-cols-2 gap-10">
                        <div class="w-full flex flex-col">
                          <input
                            type="number"
                            class="border-gray-300 border p-1"
                            value="0"
                          />
                        </div>
                        <div class="w-full flex flex-col">
                          <input
                            type="number"
                            class="border-gray-300 border p-1"
                            value="1200"
                          />
                        </div>
                      </div>
                    </div>
                  </fieldset>
                </div>

                <div
                  v-for="(section, sectionIdx) in filters"
                  :key="section.name"
                  :class="sectionIdx === 4 ? null : 'pt-10'"
                >
                  <fieldset>
                    <legend class="block text-sm font-medium text-gray-900">
                      {{ section.name }}
                    </legend>
                    <div class="pt-6 space-y-3">
                      <div
                        v-for="(option, optionIdx) in section.options"
                        :key="option.value"
                        class="flex items-center"
                      >
                        <input
                          :id="`${section.id}-${optionIdx}`"
                          :name="`${section.id}[]`"
                          :value="option.value"
                          type="checkbox"
                          class="h-4 w-4 border-gray-300 rounded text-indigo-600 focus:ring-indigo-500"
                        />
                        <label
                          :for="`${section.id}-${optionIdx}`"
                          class="ml-3 text-sm text-gray-600"
                        >
                          {{ option.label }}
                        </label>
                      </div>
                    </div>
                  </fieldset>
                </div>
              </form>
            </div>
          </div>
          <!-- Popular products -->
          <div class="w-9/12">
            <h2 class="font-semibold text-2xl mb-4">Products (21)</h2>
            <!-- Sort button -->
            <div class="text-right pb-3">
              <Menu as="div" class="relative inline-block">
                <div class="flex">
                  <MenuButton
                    class="group inline-flex justify-center text-sm font-medium text-gray-700 hover:text-gray-900"
                  >
                    Sort
                    <span class="material-symbols-outlined"> expand_more </span>
                    <ChevronDownIcon
                      class="flex-shrink-0 -mr-1 ml-1 h-5 w-5 text-gray-400 group-hover:text-gray-500"
                      aria-hidden="true"
                    />
                  </MenuButton>
                </div>

                <MenuItems
                  class="origin-top-right absolute right-0 mt-2 w-40 rounded-md shadow-2xl bg-white ring-1 ring-black ring-opacity-5 focus:outline-none z-50"
                >
                  <div class="py-1">
                    <MenuItem
                      v-for="option in sortOptions"
                      :key="option.name"
                      v-slot="{ active }"
                    >
                      <a
                        :href="option.href"
                        :class="[
                          option.current
                            ? 'font-medium text-gray-900'
                            : 'text-gray-500',
                          active ? 'bg-gray-100' : '',
                          'block px-4 py-2 text-sm',
                        ]"
                      >
                        {{ option.name }}
                      </a>
                    </MenuItem>
                  </div>
                </MenuItems>
              </Menu>
            </div>
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-5">
              <div v-for="product in products" :key="product.name">
                <div
                  class="max-w-sm rounded-lg overflow-hidden shadow-lg hover:shadow-xl px-5 py-3 border"
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
  </div>
</template>
