<script setup>
import TextReveal from "@/components/TextReveal.vue"
import TextRevealToken from "@/components/TextRevealToken.vue"

const text = "How you design, align, and build matters. Create realistic prototypes that allow for quick iteration on flows and states. Test the full, interactive experience to get better feedback."
</script>

<template>
  <div class="min-h-screen w-screen py-12">
    <div class="pb-24 text-center text-sm text-white/30">Scroll down</div>

    <TextReveal v-slot="{ tokens }" :body="text" class="relative mx-auto h-[200vh] w-full max-w-lg">
      <div
        class="sticky left-0 top-0 flex h-1/2 items-center text-3xl font-medium leading-tight text-white">
        <div>
          <TextRevealToken
            v-for="(token, index) in tokens"
            v-slot="{ isActive }"
            :key="index"
            :index="index">
            <span
              :class="{
                'opacity-10': !isActive,
              }"
              class="transition"
              v-html="token"></span>
          </TextRevealToken>
        </div>
      </div>
    </TextReveal>
  </div>
</template>
