<script setup lang="ts">
const { wishlistLink } = useAuth();
</script>

<template>
  <nav>
    <NuxtLink class="hover:text-blue-500" to="/">{{ $t('messages.general.home') }}</NuxtLink>
    <NuxtLink class="hover:text-blue-500" to="/products">{{ $t('messages.general.allProducts') }}</NuxtLink>
    <NuxtLink class="hover:text-blue-500" to="/categories">{{ $t('messages.shop.category', 2) }}</NuxtLink>
    <NuxtLink class="hover:text-blue-500" to="/contact">{{ $t('messages.general.contact') }}</NuxtLink>
    <NuxtLink class="lg:hidden" :to="wishlistLink" :prefetch="false">Wishlist</NuxtLink>
    <NuxtLink class="lg:hidden" to="/my-account" :prefetch="false">My Account</NuxtLink>
  </nav>
</template>
