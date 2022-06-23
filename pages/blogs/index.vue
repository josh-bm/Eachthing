<script setup>
const features = [
  {
    title: "5 Eco-friendly products to help you live a little greener",
    href: "#",
    category: { name: "Article", href: "#" },
    description:"Only a small percentage of our planet’s plastics are actually recycled. Buying less single-use plastic can help reduce the waste.",
   date: "May 12, 2022",
    datetime: "2020-03-16",
    imageUrl:
      "/ecofriendly.jpg",
    readingTime: "6 min",
    author: {
      name: "Michelle Yeoh",
      href: "#",
      imageUrl:
        "/author.jpg",
    },
  },
];
const posts = [
  {
 title: "5 Ethical And Sustainable Clothing Brands Betting Against Fast Fashion",
    href: "#",
    category: { name: "Article", href: "#" },
    description:
       "As consumers, we’ve become increasingly conscious about our purchases, channeling the power of our vocalized objections to make a positive difference for the people involved in the making of our clothes and goods.",
       date: "Mar 16, 2022",
    datetime: "2020-03-16",
    imageUrl:
      "/sustainablefashion.jpg",
    readingTime: "6 min",
    author: {
      name: "Roel Aufderehar",
      href: "#",
      imageUrl:
        "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80",
    },
  },
  {
    title: "48 Eco Friendly Products You Can Buy Today to Help Stop Plastic Pollution",
    href: "#",
    category: { name: "Video", href: "#" },
    description:"We put together this list of eco friendly products to show you just how easy it can be to replace some of the plastic products you buy and support those making products out of recycled plastic. By replacing them, you can virtually eliminate your single use plastic waste in that area. By purchasing recycled plastic products you are helping to close the loop of the circular economy.",
      date: "Mar 10, 2020",
    datetime: "2020-03-10",
    imageUrl:
      "/trees.jpg",
    readingTime: "4 min",
    author: {
      name: "Brenna Goyette",
      href: "#",
      imageUrl:
        "https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80",
    },
  },
  {
    title: "Game-Changing Sustainable Brands",
    href: "#",
    category: { name: "Case Study", href: "#" },
    description:"The fifty sustainable brands we include on the Lazy E List are a cut above. They elevate design and sustainability. They effortlessly enable us to align our lifestyles with our values about the environment and society. Their sustainable products don’t just fit our lives; they change them for the better.",
       date: "Feb 12, 2020",
    datetime: "2020-02-12",
    imageUrl:
      "/blog3.webp",
    readingTime: "11 min",
    author: {
      name: "Daniela Metz",
      href: "#",
      imageUrl:
        "https://images.unsplash.com/photo-1487412720507-e7ab37603c6f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80",
    },
  },
];
</script>

<template>
  <div>
    <Navbar />

    <div class="relative mx-auto w-10/12 p-5">
      <div class="w-full">
        <nuxt-link to="/blogs/blog1">
        <div
          v-for="feature in features"
          :key="feature.name"
          class="rounded-lg shadow-lg lg:flex cursor-pointer hover:shadow-xl"
        >
          <img
            class="h-80 w-full object-cover rounded-l-lg shadow-l-lg"
            :src="feature.imageUrl"
            alt=""
          />

          <div class="px-5 pt-3 pb-5 flex flex-col justify-between space-y-5">
            <div>
              <p class="font-bold text-3xl mb-3">
                {{ feature.title }}
              </p>

              <p>
                {{ feature.description }}
              </p>
            </div>

            <div class="flex items-center">
              <img
                class="w-10 h-10 rounded-full mr-2"
                :src="feature.author.imageUrl"
                :alt="feature.authorImgAlt"
              />
              <div>
                <p class="text-sm">{{ feature.author.name }}</p>
                <p class="text-xs">{{ feature.date }} &middot; {{feature.readingTime}} read</p>
              </div>
            </div>
          </div>
        </div>
        </nuxt-link>
      </div>

      <div class="mt-12 mx-auto grid grid-cols-1 gap-10 lg:grid-cols-3">
        <div
          v-for="post in posts"
          :key="post.title"
          class="flex flex-col rounded-lg shadow-lg cursor-pointer hover:shadow-xl"
        >
          <div class="flex-shrink-0">
            <img class="h-48 w-full rounded-t-lg object-cover" :src="post.imageUrl" alt="" />
          </div>
          <div class="flex-1 bg-white p-6 flex flex-col justify-between">
            <div class="flex-1">
              <a :href="post.href" class="block mt-2">
                <p class="text-xl font-semibold text-gray-900">
                  {{ post.title }}
                </p>
                <p class="mt-3 text-base text-gray-500">
                  {{ post.description }}
                </p>
              </a>
            </div>
            <div class="mt-6 flex items-center">
              <div class="flex-shrink-0">
                <a :href="post.author.href">
                  <span class="sr-only">{{ post.author.name }}</span>
                  <img
                    class="h-10 w-10 rounded-full"
                    :src="post.author.imageUrl"
                    alt=""
                  />
                </a>
              </div>
              <div class="ml-3">
                <p class="text-sm font-medium text-gray-900">
                  <a :href="post.author.href" class="hover:underline">
                    {{ post.author.name }}
                  </a>
                </p>
                <div class="flex space-x-1 text-sm text-gray-500">
                  <time :datetime="post.datetime">
                    {{ post.date }}
                  </time>
                  <span aria-hidden="true"> &middot; </span>
                  <span> {{ post.readingTime }} read </span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
