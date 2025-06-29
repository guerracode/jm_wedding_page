<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline'

const navigation = [
  { name: 'Mensaje', href: '#Mensaje', current: false },
  { name: 'Galeria', href: '#Galeria', current: false },
  { name: 'Evento', href: '#Evento', current: false },
  { name: 'Regalos', href: '#Regalos', current: false },
  { name: 'Vestimenta', href: '#Vestimenta', current: false },
  { name: 'Confirmar', href: '#Confirmar', current: false },
]
</script>

<template>
  <div class="w-full">
    <Disclosure as="nav" class="bg-jm-secondary" v-slot="{ open }">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="flex h-16 items-center justify-between">
          <div class="flex items-center justify-between w-full">
            <div class="shrink-0">
              <p class="text-xl font-parisienne text-jm-primary">J&M</p>
            </div>
            <div class="hidden md:block">
              <div class="ml-10 flex items-baseline space-x-4">
                <a
                  v-for="item in navigation"
                  :key="item.name"
                  :href="item.href"
                  class="rounded-md px-3 py-2 text-jm-primary text-base font-parisienne"
                  :aria-current="item.current ? 'page' : undefined"
                  >{{ item.name }}</a
                >
              </div>
            </div>
          </div>
          <div class="-mr-2 flex md:hidden">
            <!-- Mobile menu button -->
            <DisclosureButton
              class="relative inline-flex items-center justify-center rounded-md bg-jm-secondary p-2 text-jm-primary hover:text-black focus:ring-2 focus:ring-jm-primary focus:ring-offset-2 focus:ring-offset-jm-primary focus:outline-hidden"
            >
              <span class="absolute -inset-0.5" />
              <span class="sr-only">Open main menu</span>
              <Bars3Icon v-if="!open" class="block size-6" aria-hidden="true" />
              <XMarkIcon v-else class="block size-6" aria-hidden="true" />
            </DisclosureButton>
          </div>
        </div>
      </div>

      <DisclosurePanel class="md:hidden border-1 rounded-md border-jm-primary m-2">
        <div class="space-y-1 px-2 pt-2 pb-3 sm:px-3">
          <DisclosureButton
            v-for="item in navigation"
            :key="item.name"
            as="a"
            :href="item.href"
            class="block rounded-md px-3 py-2 text-jm-primary text-base font-parisienne"
            :aria-current="item.current ? 'page' : undefined"
            >{{ item.name }}</DisclosureButton
          >
        </div>
      </DisclosurePanel>
    </Disclosure>
  </div>
</template>
