<script setup lang="ts">
import { ref } from "vue";
import {
  TabGroup,
  TabList,
  Tab,
  TabPanels,
  TabPanel,
  RadioGroup,
  RadioGroupLabel,
  RadioGroupDescription,
  RadioGroupOption,
} from "@headlessui/vue";

const pages = [
  { name: "Beauty", href: "#", current: false },
  { name: "Bodywash", href: "#", current: true },
];

const categories = ref({
  Description: [
    {
      id: 1,
      description:
        "This product is made from ingredients of natural origin with a scent of pomegranate from natural essential oils. Contains organic aloe vera and glycering. Leaves your skin soft and clean with a scent of pomegranate from natural essential oils.",
      icons: [
        {
          url: "https://files.eachthing.com/proofs/27/tmb/SSsTwKxxfdJBiH3QtW3vQ4qwsHTEUG3RfljCtBNg.png",
        },
        {
          url: "https://files.eachthing.com/proofs/8/tmb/zjWHhaDorHs2bMVhxmSoetyTcXa2FbjWatG9ZVBc.png",
        },
      ],
    },
  ],
  Specifications: [
    {
      id: 2,
      description: "",
      icons: [
        {
          url: "",
        },
      ],
    },
  ],
  Reviews: [
    {
      id: 3,
      description: "",
      icons: [
        {
          url: "",
        },
      ],
    },
  ],
});

const reviews = {
  average: 4,
  totalCount: 1624,
  counts: [
    { rating: 5, count: 1019 },
    { rating: 4, count: 162 },
    { rating: 3, count: 97 },
    { rating: 2, count: 199 },
    { rating: 1, count: 147 },
  ],
  featured: [
    {
      id: 1,
      rating: 5,
      content: `
        <p>This is the best bodywash I have ever tried.</p>
      `,
      author: "Emily Selman",
      avatarSrc:
        "https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=256&h=256&q=80",
    },
    {
      id: 2,
      rating: 5,
      content: `
        <p>This is the best bodywash I have ever tried.</p>
      `,
      author: "Emily Selman",
      avatarSrc:
        "https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=256&h=256&q=80",
    },

    {
      id: 3,
      rating: 5,
      content: `
        <p>This is the best bodywash I have ever tried.</p>
      `,
      author: "Emily Selman",
      avatarSrc:
        "https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=256&h=256&q=80",
    },
  ],
};

const variants = [
  {
    name: "Pomegranate",
  },
  {
    name: "Free and Clear",
  },
  {
    name: "Wild Lavender",
  },
];

const selected = ref(variants[0]);

const webshops = [
  {
    id: 1,
    title: "proshop.dk",
    logo: "/proshop.png",
    product: "Nordic Eco Care Bodywash Pomegranate 500ml",
    price: 25,
    stock: true,
    fragt: "free",
  },
  {
    id: 2,
    title: "matas.dk",
    logo: "/matas.png",
    product: "Nordic Eco Care Bodywash Pomegranate 500ml",
    price: 29,
    stock: true,
    fragt: "55 kr.",
  },
  {
    id: 3,
    title: "bilka.dk",
    logo: "/bilka.png",
    product: "Nordic Eco Care Bodywash Pomegranate 500ml",
    price: 29,
    stock: false,
    fragt: "55 kr.",
  },
];
</script>

<template>
  <div>
    <Navbar />

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
      <!-- Product start -->
      <div class="lg:flex">
        <div class="w-full flex">
          <div class="grid gap-5">
            <img
              class="w-full bg-gray-100 border border-gray-300 shadow-lg rounded-lg hover:shadow-xl cursor-pointer"
              src="/bodywash.png"
              alt=""
            />
          </div>

          <img
            class="w-9/12 scale-75 cursor-pointer"
            src="/bodywash.png"
            alt=""
          />
        </div>
        <div class="w-full p-5">
          <p>Nordic EcoClean</p>
          <h2 class="text-2xl mb-1 font-semibold">Eco Care Bodywash</h2>
          <div class="mb-5 flex items-center">
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
              star_half
            </span>
            <span class="ml-1 text-sm">4,5 (250 reviews)</span>
          </div>
          <div class="mx-auto w-full">
            <!-- Variants -->
            <RadioGroup v-model="selected">
              <RadioGroupLabel class="sr-only"></RadioGroupLabel>
              <div class="space-y-5 lg:flex lg:space-y-0 lg:space-x-2 mb-8">
                <RadioGroupOption
                  as="template"
                  v-for="variant in variants"
                  :key="variant.name"
                  :value="variant"
                  v-slot="{ active, checked }"
                >
                  <div
                    :class="[
                      active
                        ? 'ring-2 ring-white ring-opacity-60 ring-offset-2 ring-offset-teal-500'
                        : '',
                      checked ? 'bg-teal-800 text-white ' : 'bg-white ',
                    ]"
                    class="relative flex cursor-pointer rounded-lg px-3 py-3 lg:px-5 lg:py-4 shadow-md focus:outline-none"
                  >
                    <div class="flex w-full items-center justify-between">
                      <div class="flex items-center">
                        <div class="text-sm">
                          <RadioGroupLabel
                            as="p"
                            :class="checked ? 'text-white' : 'text-gray-900'"
                            class="font-medium"
                          >
                            {{ variant.name }}
                          </RadioGroupLabel>
                        </div>
                      </div>
                      <div v-show="checked" class="shrink-0 text-white">
                        <svg
                          class="ml-2 h-6 w-6"
                          viewBox="0 0 24 24"
                          fill="none"
                        >
                          <circle
                            cx="12"
                            cy="12"
                            r="12"
                            fill="#fff"
                            fill-opacity="0.2"
                          />
                          <path
                            d="M7 13l3 3 7-7"
                            stroke="#fff"
                            stroke-width="1.5"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                          />
                        </svg>
                      </div>
                    </div>
                  </div>
                </RadioGroupOption>
              </div>
            </RadioGroup>
          </div>

          <div class="w-full">
            <!-- Tabs -->
            <TabGroup>
              <TabList class="flex space-x-5 rounded-xl">
                <Tab
                  v-for="category in Object.keys(categories)"
                  as="template"
                  :key="category"
                  v-slot="{ selected }"
                >
                  <button
                    :class="[
                      'py-2.5 text-sm leading-5 text-gray-900 border-b-2',
                      'ring-white ring-opacity-60 ring-offset-2 ring-offset-blue-400 focus:outline-none focus:ring-2',
                      selected
                        ? 'bg-white border-green-700 font-semibold'
                        : 'text-gray-500 font-medium border-white hover:text-gray-900',
                    ]"
                  >
                    {{ category }}
                  </button>
                </Tab>
              </TabList>

              <TabPanels class="mt-2 w-full">
                <TabPanel
                  v-for="(posts, idx) in Object.values(categories)"
                  :key="idx"
                  :class="[]"
                >
                  <ul class="pt-2">
                    <li
                      v-for="post in posts"
                      :key="post.id"
                      class="relative rounded-md overflow-y-auto h-72"
                    >
                      <div v-if="post.id == 1" class="pr-40">
                        <h3 class="text-sm font-medium leading-5">
                          {{ post.description }}
                        </h3>

                        <ul class="mt-1 flex">
                          <img
                            v-for="icon in post.icons"
                            :src="icon.url"
                            class="w-3/12 rounded-full p-5"
                            alt=""
                          />
                        </ul>
                      </div>

                      <div
                        v-else-if="post.id == 2"
                        class="text-sm font-medium leading-5"
                      >
                        <p>International list of ingredients (INCI)</p>
                        <p>
                          INCI: Aqua, Sodium coco-sulfate, Lauryl glucoside,
                          Coco glucoside,
                        </p>

                        <p>
                          Cocamidopropyl betaine, Glycerin**, Aloe barbadensis
                          leaf juice*
                        </p>

                        <p>
                          Hydrolyzed wheat protein, Lactic acid, Sodium
                          chloride, Betaine,
                        </p>

                        <p>
                          Sodium levulinate, Potassium sorbate, Parfum
                          (Limonene)
                        </p>
                        <br />
                        <p>* Ingredient from organic farming</p>

                        <p>** Made using organic ingredients</p>

                        <p>99,2 % natural origin of total</p>

                        <p>11 % organic of total</p>
                      </div>

                      <div v-else-if="post.id == 3" class="pr-5 space-y-10">
                        <div
                          v-for="review in reviews.featured"
                          :key="review.id"
                          class=""
                        >
                          <div class="flex items-center">
                            <img
                              :src="review.avatarSrc"
                              :alt="`${review.author}.`"
                              class="h-10 w-10 rounded-full"
                            />
                            <div class="ml-4">
                              <h4 class="text-sm font-bold text-gray-900">
                                {{ review.author }}
                              </h4>
                              <div class="mt-1 flex items-center">
                                <span
                                  v-for="rating in [0, 1, 2, 3, 4]"
                                  :key="rating"
                                  :class="[
                                    reviews.average > rating
                                      ? 'text-yellow-400'
                                      : 'text-gray-300',
                                    'flex-shrink-0 h-5 w-5',
                                  ]"
                                  aria-hidden="true"
                                  class="material-symbols-outlined"
                                >
                                  star
                                </span>
                              </div>
                            </div>
                          </div>

                          <div
                            class="mt-4 space-y-6 text-base italic text-gray-600"
                            v-html="review.content"
                          />
                        </div>

                        <div class="mt-10">
                          <h3 class="text-lg font-medium text-gray-900">
                            Share your thoughts
                          </h3>
                          <p class="mt-1 text-sm text-gray-600">
                            If you’ve used this product, share your thoughts
                            with other customers
                          </p>

                          <a
                            href="#"
                            class="mt-6 inline-flex w-full bg-white border border-gray-300 rounded-md py-2 px-8 items-center justify-center text-sm font-medium text-gray-900 hover:bg-gray-50 sm:w-auto lg:w-full"
                            >Write a review</a
                          >
                        </div>
                      </div>
                    </li>
                  </ul>
                </TabPanel>
              </TabPanels>
            </TabGroup>
          </div>
        </div>
      </div>
    </div>

    <!-- Webshop start -->
    <div class="bg-gray-50">
      <div class="w-10/12 mx-auto px-5 pt-10 pb-5">
        <ul role="list" class="grid grid-cols-1 gap-6">
          <li v-for="webshop in webshops" :key="webshop.id">
            <a
              href="#"
              class="block group bg-white rounded-lg p-5 shadow-md hover:shadow-lg"
            >
              <div class="lg:flex space-y-5 lg:space-y-0 justify-between items-center w-full">
                <div class="flex space-x-5 items-center">
                  <figure class="w-40">
                    <img :src="webshop.logo" class="w-full scale-75" alt="" />
                  </figure>
                  <p class="text-md lg:text-lg font-medium w-full">
                    {{ webshop.product }}
                  </p>
                </div>

                <div class="flex items-center justify-end space-x-5">
                  <div class="w-40">
                    <div v-if="webshop.stock" class="flex space-x-2">
                      <span
                        class="material-symbols-outlined stock text-green-500"
                        >check_circle</span
                      >
                      <span class="text-sm lg:text-base">In stock</span>
                    </div>

                    <div v-else class="flex space-x-2">
                      <span class="material-symbols-outlined stock text-red-500"
                        >cancel</span
                      >
                      <span>Out of stock</span>
                    </div>
                  </div>

                  <div class="w-32 text-right">
                    <p class="text-sm lg:text-lg font-semibold">{{ webshop.price }} kr.</p>

                    <p class="text-sm font-medium text-gray-400">
                      {{ webshop.fragt }} delivery
                    </p>
                  </div>

                  <button
                    type="button"
                    class="border border-transparent rounded-lg shadow-sm text-white bg-green-700 hover:bg-green-600 focus:outline-none"
                  >
                    <a
                      href="https://www.bilkatogo.dk/produkt/Eco-Care-Nordic-H%C3%A5nds%C3%A6be-m.-aloe-vera-og-lavendel/78322/"
                    class="inline-flex items-center pl-4 pr-2 py-3 text-sm font-medium "
                    target="_blank"
                    >
                      <span class="text-xs">Visit Site</span>  
                      <span class="material-symbols-outlined">
                        keyboard_arrow_right
                      </span>
                    </a>
                  </button>
                </div>
              </div>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style>
.stock {
  font-variation-settings: "FILL" 1, "wght" 400, "GRAD" 0, "opsz" 48;
}
</style>
