<script setup>
const categories = [
  {
    name: "Apparel",
    href: "#",
    imageSrc: "/apparel.jpg",
  },
  {
    name: "Baby products",
    href: "#",
    imageSrc: "/baby.jpg",
  },
  {
    name: "Beauty",
    href: "#",
    imageSrc: "/beauty.jpg",
  },
  {
    name: "Beverage",
    href: "#",
    imageSrc: "/beverage.jpg",
  },
  {
    name: "Electronics",
    href: "#",
    imageSrc: "/electronics.jpg",
  },
  {
    name: "Food",
    href: "#",
    imageSrc: "/food.jpg",
  },
  {
    name: "Household",
    href: "#",
    imageSrc: "/household.jpg",
  },
  {
    name: "Home",
    href: "#",
    imageSrc: "/home.jpg",
  },
  {
    name: "Personal care",
    href: "#",
    imageSrc: "/personalcare.jpg",
  },
  {
    name: "Pet",
    href: "#",
    imageSrc: "/pet.jpg",
  },
  {
    name: "Sport",
    href: "#",
    imageSrc: "/sport.jpg",
  },
  {
    name: "Miscellaneous",
    href: "#",
    imageSrc: "/misc.jpg",
  },
];
</script>

<template>
  <div>
    <Navbar />

    <div>
      <div class="w-10/12 mx-auto p-5">
        <div
          class="px-4 sm:px-6 sm:flex sm:items-center sm:justify-between lg:px-8 xl:px-0"
        >
          <h2 class="font-semibold text-2xl mb-4">Shop by Category</h2>
          <!-- <a
            href="#"
            class="hidden text-sm font-semibold text-indigo-600 hover:text-indigo-500 sm:block"
            >Browse all categories<span aria-hidden="true"> &rarr;</span></a
          > -->
        </div>

        <div
          class="px-4 grid gap-5 grid-cols-1 lg:grid-cols-4 lg:space-x-8 lg:px-8"
        >
          <a
            v-for="category in categories"
            :key="category.name"
            href="/categories/beauty"
            class="relative lg:w-56 h-80 rounded-lg p-6 flex flex-col overflow-hidden hover:opacity-75 xl:w-auto"
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
      </div>
    </div>
  </div>
</template>
