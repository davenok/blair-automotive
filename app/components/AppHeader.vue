<template>
  <header class="sticky top-0 z-50 bg-[#1a1a1a] border-b border-[#2d2d2d]">
    <div class="container-mobile">
      <div class="flex items-center justify-between h-16 md:h-20">
        <!-- Logo -->
        <NuxtLink to="/" class="flex-shrink-0">
          <img
            src="/blair-logo.svg"
            alt="Blair Automotive Services"
            class="h-10 md:h-12 w-auto"
          />
        </NuxtLink>

        <!-- Quick Actions (Mobile) -->
        <div class="flex items-center gap-2 md:hidden">
          <UButton
            icon="i-lucide-phone"
            color="red"
            variant="solid"
            size="lg"
            aria-label="Call us"
            to="tel:+1234567890"
            external
            class="bg-[#C41E3A] hover:bg-[#9B1829]"
          />
          <UButton
            icon="i-lucide-menu"
            color="gray"
            variant="ghost"
            size="lg"
            aria-label="Open menu"
            @click="isMenuOpen = !isMenuOpen"
          />
        </div>

        <!-- Desktop Navigation -->
        <nav class="hidden md:flex items-center gap-6">
          <NuxtLink
            v-for="item in navItems"
            :key="item.to"
            :to="item.to"
            class="text-[#F5F5DC] hover:text-[#C41E3A] transition-colors font-medium"
          >
            {{ item.label }}
          </NuxtLink>
        </nav>

        <!-- Desktop Actions -->
        <div class="hidden md:flex items-center gap-3">
          <UButton
            icon="i-lucide-phone"
            color="gray"
            variant="ghost"
            to="tel:+1234567890"
            external
            class="text-[#F5F5DC]"
          >
            (555) 123-4567
          </UButton>
          <UButton
            color="red"
            size="lg"
            class="bg-[#C41E3A] hover:bg-[#9B1829]"
            @click="openAppointmentModal"
          >
            Schedule Service
          </UButton>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition
      enter-active-class="transition-all duration-200"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition-all duration-150"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <div
        v-if="isMenuOpen"
        class="md:hidden border-t border-[#2d2d2d] bg-[#1a1a1a]"
      >
        <nav class="container-mobile py-4 space-y-1">
          <NuxtLink
            v-for="item in navItems"
            :key="item.to"
            :to="item.to"
            class="block py-3 text-[#F5F5DC] hover:text-[#C41E3A] transition-colors font-medium text-lg"
            @click="isMenuOpen = false"
          >
            {{ item.label }}
          </NuxtLink>
          <div class="pt-4 border-t border-[#2d2d2d] mt-4">
            <UButton
              color="red"
              size="lg"
              block
              class="bg-[#C41E3A] hover:bg-[#9B1829] w-full"
              @click="openAppointmentModal"
            >
              Schedule Service
            </UButton>
          </div>
        </nav>
      </div>
    </Transition>
  </header>
</template>

<script setup lang="ts">
const isMenuOpen = ref(false)

const navItems = [
  { label: 'Home', to: '/' },
  { label: 'Services', to: '/services' },
  { label: 'About', to: '/about' },
  { label: 'Contact', to: '/contact' },
]

function openAppointmentModal() {
  isMenuOpen.value = false
  // TODO: Open appointment modal
  console.log('Open appointment modal')
}
</script>
