<script setup>
import { ref } from "vue";

import {
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
  Dialog,
  DialogPanel,
  DialogTitle,
  TransitionChild,
  TransitionRoot,
} from "@headlessui/vue";

const navigation = [
  { name: "Categories", href: "/categories" },
  { name: "Guides", href: "/blogs" },
];

const up = ref(false);
</script>

<template>
  <div class="w-10/12 py-5 mx-auto">
    <TransitionRoot as="template" :show="up">
      <Dialog as="div" class="relative z-10" @close="up = false">
        <TransitionChild
          as="template"
          enter="ease-out duration-300"
          enter-from="opacity-0"
          enter-to="opacity-100"
          leave="ease-in duration-200"
          leave-from="opacity-100"
          leave-to="opacity-0"
        >
          <div
            class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity"
          />
        </TransitionChild>

        <div class="fixed z-10 inset-0 overflow-y-auto">
          <div
            class="flex items-end sm:items-center justify-center min-h-full p-4 text-center sm:p-0"
          >
            <TransitionChild
              as="template"
              enter="ease-out duration-300"
              enter-from="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
              enter-to="opacity-100 translate-y-0 sm:scale-100"
              leave="ease-in duration-200"
              leave-from="opacity-100 translate-y-0 sm:scale-100"
              leave-to="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
            >
              <DialogPanel
                class="relative bg-white rounded-lg px-4 pt-5 pb-4 text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:max-w-lg sm:w-full sm:p-6"
              >
                <div class="hidden sm:block absolute top-0 right-0 pt-4 pr-4">
                  <button class="modal-default-button" @click="up = false">
                    <span class="material-symbols-outlined"> close </span>
                  </button>
                </div>
                <div
                  class="bg-white py-8 px-4 flex flex-col space-y-5 sm:px-10"
                >
                  <figure class="w-10 mx-auto">
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
                  <h2
                    class="mt-6 text-center text-2xl font-extrabold text-gray-900"
                  >
                    Personalize your experience
                  </h2>
                  <p class="mb-5 text-center text-sm text-gray-600">
                    Log in to your Eachthing account.
                  </p>

                  <form class="space-y-6" action="#" method="POST">
                    <div>
                      <label
                        for="email"
                        class="block text-sm font-medium text-gray-700"
                      >
                        Email address
                      </label>
                      <div class="mt-1">
                        <input
                          id="email"
                          name="email"
                          type="email"
                          autocomplete="email"
                          required=""
                          class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                        />
                      </div>
                    </div>

                    <div>
                      <label
                        for="password"
                        class="block text-sm font-medium text-gray-700"
                      >
                        Password
                      </label>
                      <div class="mt-1">
                        <input
                          id="password"
                          name="password"
                          type="password"
                          autocomplete="current-password"
                          required=""
                          class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                        />
                      </div>
                    </div>

                    <div class="flex items-center justify-between">
                      <div class="flex items-center">
                        <input
                          id="remember-me"
                          name="remember-me"
                          type="checkbox"
                          class="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-gray-300 rounded"
                        />
                        <label
                          for="remember-me"
                          class="ml-2 block text-sm text-gray-900"
                        >
                          Remember me
                        </label>
                      </div>

                      <div class="text-sm">
                        <a
                          href="#"
                          class="font-medium text-indigo-600 hover:text-indigo-500"
                        >
                          Forgot your password?
                        </a>
                      </div>
                    </div>

                    <div>
                      <button
                        type="submit"
                        class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                      >
                        Sign in
                      </button>
                    </div>
                  </form>

                  <div class="mt-6">
                    <div class="relative">
                      <div class="absolute inset-0 flex items-center">
                        <div class="w-full border-t border-gray-300" />
                      </div>
                      <div class="relative flex justify-center text-sm">
                        <span class="px-2 bg-white text-gray-500">
                          Or continue with
                        </span>
                      </div>
                    </div>

                    <div class="mt-6 grid grid-cols-3 gap-3">
                      <div>
                        <a
                          href="#"
                          class="w-full inline-flex justify-center py-2 px-4 border border-gray-300 rounded-md shadow-sm bg-white text-sm font-medium text-gray-500 hover:bg-gray-50"
                        >
                          <span class="sr-only">Sign in with Facebook</span>
                          <svg
                            class="w-5 h-5"
                            aria-hidden="true"
                            fill="currentColor"
                            viewBox="0 0 20 20"
                          >
                            <path
                              fill-rule="evenodd"
                              d="M20 10c0-5.523-4.477-10-10-10S0 4.477 0 10c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V10h2.54V7.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V10h2.773l-.443 2.89h-2.33v6.988C16.343 19.128 20 14.991 20 10z"
                              clip-rule="evenodd"
                            />
                          </svg>
                        </a>
                      </div>

                      <div>
                        <a
                          href="#"
                          class="w-full inline-flex justify-center py-2 px-4 border border-gray-300 rounded-md shadow-sm bg-white text-sm font-medium text-gray-500 hover:bg-gray-50"
                        >
                          <span class="sr-only">Sign in with Twitter</span>
                          <svg
                            class="w-5 h-5"
                            aria-hidden="true"
                            fill="currentColor"
                            viewBox="0 0 20 20"
                          >
                            <path
                              d="M6.29 18.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0020 3.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.073 4.073 0 01.8 7.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 010 16.407a11.616 11.616 0 006.29 1.84"
                            />
                          </svg>
                        </a>
                      </div>

                      <div>
                        <a
                          href="#"
                          class="w-full inline-flex justify-center py-2 px-4 border border-gray-300 rounded-md shadow-sm bg-white text-sm font-medium text-gray-500 hover:bg-gray-50"
                        >
                          <span class="sr-only">Sign in with GitHub</span>
                          <svg
                            class="w-5 h-5"
                            aria-hidden="true"
                            fill="currentColor"
                            viewBox="0 0 20 20"
                          >
                            <path
                              fill-rule="evenodd"
                              d="M10 0C4.477 0 0 4.484 0 10.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0110 4.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.203 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.942.359.31.678.921.678 1.856 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0020 10.017C20 4.484 15.522 0 10 0z"
                              clip-rule="evenodd"
                            />
                          </svg>
                        </a>
                      </div>
                    </div>
                  </div>
                </div>
              </DialogPanel>
            </TransitionChild>
          </div>
        </div>
      </Dialog>
    </TransitionRoot>

    <Disclosure as="nav" v-slot="{ open }">
      <div class="flex justify-between">
        <div
          class="hidden w-full lg:flex lg:items-center lg:space-x-8 lg:justify-between"
        >
          <div class="flex items-center space-x-5">
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
            <a
              v-for="item in navigation"
              :key="item.name"
              :href="item.href"
              :class="[
                item.current ? '' : ' hover:text-teal-800',
                'px-3 py-2 rounded-md text-lg font-medium',
              ]"
              :aria-current="item.current ? 'page' : undefined"
              >{{ item.name }}</a
            >
          </div>

          <div class="w-7/12">
            <form action="/search">
              <label for="search" class="sr-only">Search</label>
              <div class="relative">
                <div
                  class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
                >
                  <span class="material-symbols-outlined"> search </span>
                </div>

                <input
                  id="search"
                  name="search"
                  class="block w-full pl-10 pr-3 py-2 border border-gray-300 rounded-md leading-5 bg-white placeholder-gray-500 focus:outline-none focus:placeholder-gray-400 sm:text-sm"
                  placeholder="Search"
                  type="search"
                />
              </div>
            </form>
          </div>

          <div class="flex items-center space-x-5">
            <nuxt-link
              to=""
              @click="up = true"
              class="cursor-pointer text-lg font-medium hover:text-teal-800"
              >Log in</nuxt-link
            >

            <button
              type="button"
              @click="up = true"
              class="button bg-teal-800 hover:bg-teal-900 text-white p-3 rounded-lg shadow-lg block"
            >
              Sign up
            </button>
          </div>
        </div>

        <div class="flex justify-between items-center lg:hidden">
          <!-- Mobile menu button -->
          <DisclosureButton
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
          >
            <span class="sr-only">Open main menu</span>
            <span v-if="!open" class="material-symbols-outlined"> menu </span>

            <span v-else class="material-symbols-outlined"> close </span>
          </DisclosureButton>
        </div>
      </div>

      <DisclosurePanel class="lg:hidden w-full">
        <div class="pt-2 pb-3 space-y-1">
          <nuxt-link
            to="/"
            class="block pl-3 pr-4 py-2 hover:bg-teal-800 hover:text-white text-base font-medium"
          >
            Home
          </nuxt-link>
          <DisclosureButton
            as="a"
            v-for="item in navigation"
            :key="item.name"
            :href="item.href"
            class="block pl-3 pr-4 py-2 hover:bg-teal-800 hover:text-white text-base font-medium"
            >{{ item.name }}</DisclosureButton
          >
        </div>
        <div class="pt-4 pb-3 px-4 border-t border-gray-200 space-y-5">
          <nuxt-link
            to=""
            @click="up = true"
            class="cursor-pointer font-medium hover:text-teal-800"
            >Log in</nuxt-link
          >

          <button
            type="button"
            @click="up = true"
            class="button bg-teal-800 hover:bg-teal-900 text-white p-3 rounded-lg shadow-lg block"
          >
            Sign up
          </button>
        </div>
      </DisclosurePanel>
    </Disclosure>
  </div>
</template>
