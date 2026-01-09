<template>
  <div>
    <!-- Hero Section -->
    <section class="relative bg-[#1a1a1a] text-[#F5F5DC] py-16 md:py-32 lg:py-40 overflow-hidden">
      <!-- Background Pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute inset-0" style="background-image: url('data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='1'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E')"></div>
      </div>
      
      <div class="container-mobile relative">
        <div class="text-center max-w-5xl mx-auto">
          <div class="inline-flex items-center gap-2 px-5 py-2.5 bg-[#2d2d2d] rounded-full mb-8 md:mb-10">
            <UIcon name="i-lucide-wrench" class="text-[#C41E3A] text-lg" />
            <span class="text-sm md:text-base font-medium">Family Owned Since 1985</span>
          </div>
          
          <h1 class="text-4xl md:text-6xl lg:text-7xl xl:text-8xl font-bold mb-6 md:mb-10 leading-tight">
            Honest Auto Service<br />
            <span class="text-[#C41E3A]">You Can Trust</span>
          </h1>
          
          <p class="text-lg md:text-xl lg:text-2xl text-[#9BA3A8] mb-10 md:mb-12 max-w-3xl mx-auto leading-relaxed">
            Professional automotive care with small-town values. We treat your vehicle like family.
          </p>
          
          <div class="flex flex-col sm:flex-row gap-4 md:gap-6 justify-center">
            <UButton
              size="xl"
              color="red"
              class="bg-[#C41E3A] hover:bg-[#9B1829] text-lg md:text-xl font-semibold px-8 py-4"
            >
              <UIcon name="i-lucide-calendar" class="mr-2 text-xl" />
              Schedule Service
            </UButton>
            <UButton
              size="xl"
              color="gray"
              variant="outline"
              class="border-[#F5F5DC] text-[#F5F5DC] hover:bg-[#2d2d2d] text-lg md:text-xl font-semibold px-8 py-4"
              to="tel:+19186942922"
              external
            >
              <UIcon name="i-lucide-phone" class="mr-2 text-xl" />
              (918) 694-2922
            </UButton>
          </div>
        </div>
      </div>
    </section>

    <!-- Trust Signals Bar -->
    <section class="bg-[#2d2d2d] py-8 md:py-12">
      <div class="container-mobile">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-6 md:gap-8">
          <div v-for="signal in trustSignals" :key="signal.label" class="text-center">
            <div class="flex justify-center mb-2">
              <UIcon :name="signal.icon" class="text-[#C41E3A] text-3xl md:text-4xl" />
            </div>
            <div class="text-[#F5F5DC] font-bold text-lg md:text-xl">{{ signal.value }}</div>
            <div class="text-[#9BA3A8] text-xs md:text-sm">{{ signal.label }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="py-16 md:py-24 bg-[#F5F5DC]">
      <div class="container-mobile">
        <div class="text-center mb-12">
          <h2 class="text-3xl md:text-4xl font-bold text-[#1a1a1a] mb-4">
            Our Services
          </h2>
          <p class="text-[#71797E] text-lg max-w-2xl mx-auto">
            From routine maintenance to complex repairs, we've got you covered.
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            v-for="service in services"
            :key="service.title"
            class="bg-white rounded-lg p-6 shadow-sm hover:shadow-md transition-shadow border border-[#E8E4D0]"
          >
            <div class="flex items-start gap-4">
              <div class="flex-shrink-0 w-12 h-12 bg-[#C41E3A]/10 rounded-lg flex items-center justify-center">
                <UIcon :name="service.icon" class="text-[#C41E3A] text-2xl" />
              </div>
              <div>
                <h3 class="font-bold text-lg text-[#1a1a1a] mb-2">{{ service.title }}</h3>
                <p class="text-[#71797E] text-sm leading-relaxed">{{ service.description }}</p>
              </div>
            </div>
          </div>
        </div>
        
        <div class="text-center mt-10">
          <UButton
            size="lg"
            color="red"
            variant="outline"
            class="border-[#C41E3A] text-[#C41E3A] hover:bg-[#C41E3A] hover:text-white"
          >
            View All Services
          </UButton>
        </div>
      </div>
    </section>

    <!-- Why Choose Us -->
    <section class="py-16 md:py-24 bg-white">
      <div class="container-mobile">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-3xl md:text-4xl font-bold text-[#1a1a1a] mb-6">
              Why Choose Blair Automotive?
            </h2>
            <div class="space-y-6">
              <div v-for="reason in reasons" :key="reason.title" class="flex gap-4">
                <div class="flex-shrink-0">
                  <div class="w-10 h-10 bg-[#C41E3A] rounded-full flex items-center justify-center">
                    <UIcon :name="reason.icon" class="text-white text-lg" />
                  </div>
                </div>
                <div>
                  <h3 class="font-bold text-lg text-[#1a1a1a] mb-2">{{ reason.title }}</h3>
                  <p class="text-[#71797E] leading-relaxed">{{ reason.description }}</p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="bg-[#E8E4D0] rounded-lg p-8 md:p-12">
            <h3 class="text-2xl font-bold text-[#1a1a1a] mb-6">Ready to Get Started?</h3>
            <p class="text-[#71797E] mb-6">
              Schedule your appointment today and experience the Blair difference.
            </p>
            <UButton
              size="xl"
              color="red"
              block
              class="bg-[#C41E3A] hover:bg-[#9B1829] w-full"
            >
              <UIcon name="i-lucide-calendar" class="mr-2" />
              Book Your Service
            </UButton>
            <div class="mt-6 text-center">
              <a
                href="tel:+19186942922"
                class="text-[#C41E3A] font-semibold hover:text-[#9B1829]"
              >
                Or call us: (918) 694-2922
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials -->
    <section class="py-16 md:py-24 bg-[#F5F5DC]">
      <div class="container-mobile">
        <div class="text-center mb-12">
          <h2 class="text-3xl md:text-4xl font-bold text-[#1a1a1a] mb-4">
            What Our Customers Say
          </h2>
          <p class="text-[#71797E] text-lg">
            Don't just take our word for it.
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div
            v-for="testimonial in testimonials"
            :key="testimonial.name"
            class="bg-white rounded-lg p-6 shadow-sm"
          >
            <div class="flex gap-1 mb-4">
              <UIcon
                v-for="i in 5"
                :key="i"
                name="i-lucide-star"
                class="text-[#C41E3A] fill-current"
              />
            </div>
            <p class="text-[#1a1a1a] mb-4 italic">"{{ testimonial.text }}"</p>
            <div class="font-semibold text-[#1a1a1a]">{{ testimonial.name }}</div>
            <div class="text-sm text-[#71797E]">{{ testimonial.location }}</div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
const trustSignals = [
  { icon: 'i-lucide-calendar-check', value: '40+', label: 'Years in Business' },
  { icon: 'i-lucide-users', value: '10,000+', label: 'Happy Customers' },
  { icon: 'i-lucide-shield-check', value: '100%', label: 'Quality Guaranteed' },
  { icon: 'i-lucide-award', value: 'ASE', label: 'Certified Technicians' },
]

const services = [
  {
    icon: 'i-lucide-droplet',
    title: 'Oil Changes & Fluids',
    description: 'Regular oil changes and fluid services to keep your engine running smooth.',
  },
  {
    icon: 'i-lucide-disc',
    title: 'Brake Services',
    description: 'Complete brake inspection, repair, and replacement for your safety.',
  },
  {
    icon: 'i-lucide-cpu',
    title: 'Engine Diagnostics',
    description: 'Advanced diagnostic tools to identify and fix engine issues quickly.',
  },
  {
    icon: 'i-lucide-settings',
    title: 'Transmission Service',
    description: 'Expert transmission repair and maintenance for all makes and models.',
  },
  {
    icon: 'i-lucide-circle',
    title: 'Tire Services',
    description: 'Tire sales, rotation, balancing, and alignment services.',
  },
  {
    icon: 'i-lucide-wind',
    title: 'AC & Heating',
    description: 'Climate control system repair to keep you comfortable year-round.',
  },
]

const reasons = [
  {
    icon: 'i-lucide-home',
    title: 'Family Owned & Operated',
    description: 'Three generations of automotive expertise serving our community with pride.',
  },
  {
    icon: 'i-lucide-handshake',
    title: 'Honest & Transparent',
    description: 'We explain every repair clearly and never recommend unnecessary services.',
  },
  {
    icon: 'i-lucide-wrench',
    title: 'Expert Technicians',
    description: 'ASE-certified mechanics with decades of combined experience.',
  },
  {
    icon: 'i-lucide-clock',
    title: 'Fast Turnaround',
    description: 'We respect your time and get you back on the road quickly.',
  },
]

const testimonials = [
  {
    name: 'Sarah Johnson',
    location: 'Hometown, ST',
    text: 'Blair Automotive saved me from a costly dealer repair. Honest, fair pricing and excellent service!',
  },
  {
    name: 'Mike Patterson',
    location: 'Hometown, ST',
    text: 'Been coming here for 15 years. They treat me like family and always do great work.',
  },
  {
    name: 'Lisa Chen',
    location: 'Hometown, ST',
    text: 'Finally found a mechanic I can trust! They explained everything and didn\'t try to upsell me.',
  },
]
</script>
