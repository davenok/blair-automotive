<template>
  <footer class="bg-[#1a1a1a] text-[#F5F5DC] border-t border-[#2d2d2d]">
    <div class="container-mobile py-12 md:py-16">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 md:gap-12">
        <!-- Logo & Tagline -->
        <div class="space-y-4">
          <img
            src="/blair-logo.svg"
            alt="Blair Automotive Services"
            class="h-12 w-auto"
          />
          <p class="text-[#9BA3A8] text-sm leading-relaxed">
            Family owned excellence since 1985. Honest service, fair prices.
          </p>
          <div class="flex gap-3">
            <UButton
              icon="i-lucide-facebook"
              color="gray"
              variant="ghost"
              size="sm"
              aria-label="Facebook"
              to="https://facebook.com"
              external
            />
            <UButton
              icon="i-lucide-instagram"
              color="gray"
              variant="ghost"
              size="sm"
              aria-label="Instagram"
              to="https://instagram.com"
              external
            />
          </div>
        </div>

        <!-- Quick Links -->
        <div>
          <h3 class="text-lg font-bold mb-4">Quick Links</h3>
          <ul class="space-y-2">
            <li v-for="item in quickLinks" :key="item.to">
              <NuxtLink
                :to="item.to"
                class="text-[#9BA3A8] hover:text-[#C41E3A] transition-colors"
              >
                {{ item.label }}
              </NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Services -->
        <div>
          <h3 class="text-lg font-bold mb-4">Services</h3>
          <ul class="space-y-2">
            <li v-for="service in topServices" :key="service">
              <span class="text-[#9BA3A8]">{{ service }}</span>
            </li>
          </ul>
        </div>

        <!-- Contact Info -->
        <div>
          <h3 class="text-lg font-bold mb-4">Contact Us</h3>
          <div class="space-y-3 text-[#9BA3A8]">
            <div class="flex items-start gap-3">
              <UIcon name="i-lucide-map-pin" class="text-[#C41E3A] flex-shrink-0 mt-1" />
              <div class="text-sm">
                123 Main Street<br />
                Hometown, ST 12345
              </div>
            </div>
            <div class="flex items-center gap-3">
              <UIcon name="i-lucide-phone" class="text-[#C41E3A] flex-shrink-0" />
              <a href="tel:+1234567890" class="hover:text-[#C41E3A] transition-colors">
                (555) 123-4567
              </a>
            </div>
            <div class="flex items-center gap-3">
              <UIcon name="i-lucide-mail" class="text-[#C41E3A] flex-shrink-0" />
              <a href="mailto:info@blairautomotive.com" class="hover:text-[#C41E3A] transition-colors">
                info@blairautomotive.com
              </a>
            </div>
            <div class="flex items-start gap-3">
              <UIcon name="i-lucide-clock" class="text-[#C41E3A] flex-shrink-0 mt-1" />
              <div class="text-sm">
                Mon-Fri: 8:00 AM - 6:00 PM<br />
                Sat: 9:00 AM - 4:00 PM<br />
                Sun: Closed
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom Bar -->
      <div class="mt-12 pt-8 border-t border-[#2d2d2d] flex flex-col md:flex-row justify-between items-center gap-4">
        <p class="text-[#71797E] text-sm text-center md:text-left">
          &copy; {{ currentYear }} Blair Automotive Services. All rights reserved.
        </p>
        <div class="flex gap-6 text-sm text-[#71797E]">
          <NuxtLink to="/privacy" class="hover:text-[#C41E3A] transition-colors">
            Privacy Policy
          </NuxtLink>
          <NuxtLink to="/terms" class="hover:text-[#C41E3A] transition-colors">
            Terms of Service
          </NuxtLink>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
const currentYear = new Date().getFullYear()

const quickLinks = [
  { label: 'Home', to: '/' },
  { label: 'Services', to: '/services' },
  { label: 'About Us', to: '/about' },
  { label: 'Contact', to: '/contact' },
  { label: 'Schedule Service', to: '/schedule' },
]

const topServices = [
  'Oil Changes',
  'Brake Service',
  'Engine Diagnostics',
  'Tire Service',
]
</script>
