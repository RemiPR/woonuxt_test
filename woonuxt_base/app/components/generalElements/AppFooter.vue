<script setup lang="ts">
const { wooNuxtVersionInfo } = useHelpers();
const { wishlistLink } = useAuth();
</script>

<template>
  <footer class="bg-white order-last">
    <div class="container flex flex-wrap justify-between gap-12 my-24 md:gap-24">
      <div class="mr-auto">
        <Logo />
        <WebsiteShortDescription />
        <LangSwitcher class="mt-8" />
      </div>

      <div class="w-3/7 lg:w-auto">
        <div class="mb-1 font-semibold">{{ $t('footerInformation.title') }}</div>
        <div class="text-sm">
          <a class="py-1.5 block" href="/">{{ $t('footerInformation.aboutUs') }}</a>
          <a href="/" class="py-1.5 block">{{ $t('footerInformation.careers') }}</a>
          <a href="/" class="py-1.5 block">{{ $t('footerInformation.press') }}</a>
          <a href="https://woonuxt.com/faq" class="py-1.5 block" rel="noreferrer" target="_blank">{{ $t('footerInformation.faq') }}</a>
        </div>
      </div>

      <div class="w-3/7 lg:w-auto">
        <div class="mb-1 font-semibold">{{ $t('footerProducts.title') }}</div>
        <div class="text-sm">
          <NuxtLink to="/products" class="py-1.5 block">{{ $t('footerProducts.newArrivals') }}</NuxtLink>
          <NuxtLink to="/products?filter=sale[true]" class="py-1.5 block">{{ $t('footerProducts.onSale') }}</NuxtLink>
          <NuxtLink to="/products?orderby=rating&order=ASC&filter=rating[1]" class="py-1.5 block">{{ $t('footerProducts.topRated') }}</NuxtLink>
          <a href="/" class="py-1.5 block">{{ $t('footerProducts.giftCards') }}</a>
        </div>
      </div>

      <div class="w-3/7 lg:w-auto">
        <div class="mb-1 font-semibold">{{ $t('footerCustomerService.title') }}</div>
        <div class="text-sm">
          <NuxtLink to="/contact" class="py-1.5 block">{{ $t('footerCustomerService.contactUs') }}</NuxtLink>
          <a href="/" class="py-1.5 block">{{ $t('footerCustomerService.shipping') }}</a>
          <a href="/" class="py-1.5 block">{{ $t('footerCustomerService.privacyPolicy') }}</a>
          <a href="/" class="py-1.5 block">{{ $t('footerCustomerService.termsConditions') }}</a>
        </div>
      </div>
      <div class="w-3/7 lg:w-auto">
        <div class="mb-1 font-semibold">{{ $t('messages.account.myAccount') }}</div>
        <div class="text-sm">
          <NuxtLink to="/my-account/" class="py-1.5 block">{{ $t('messages.account.myAccount') }}</NuxtLink>
          <NuxtLink to="/my-account/?tab=orders" class="py-1.5 block">{{ $t('messages.shop.orderHistory') }}</NuxtLink>
          <NuxtLink :to="wishlistLink" class="py-1.5 block">{{ $t('messages.shop.wishlist') }}</NuxtLink>
          <a href="/" class="py-1.5 block">{{ $t('messages.general.newsletter') }}</a>
        </div>
      </div>
    </div>
    <div class="container border-t flex items-center justify-center my-4 py-4">
      <div class="copywrite text-xs text-center py-2">
        <a href="https://remigijusprialgauskis.com" class="text-sm">
          {{ $t('copyright.title') }}
        </a>
      </div>
      <SocialIcons class="ml-auto" />
    </div>
  </footer>
</template>

<style scoped lang="postcss">
a {
  @apply hover:underline;
}
</style>
