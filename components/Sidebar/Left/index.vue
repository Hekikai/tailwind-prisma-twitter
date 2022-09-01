<script setup lang="ts">
import { HomeIcon } from '@heroicons/vue/20/solid'
import {
  HashtagIcon,
  InboxIcon,
  BookmarkIcon,
  DocumentTextIcon,
  UserIcon,
  BellIcon,
  InformationCircleIcon,
} from '@heroicons/vue/24/outline'
import useTailwindConfig from '~/composables/useTailwindConfig'

const { defaultTransition } = useTailwindConfig()
</script>

<template>
  <div class="h-screen flex flex-col">
    <div
      class="p-2 my-2 hover:bg-blue-50 rounded-full w-min dark:hover:bg-white/20"
      :class="defaultTransition"
    >
      <nuxt-link to="/">
        <div class="w-8 h-8">
          <logo-twitter />
        </div>
      </nuxt-link>
    </div>

    <div class="mt-2 space-y-3">
      <sidebar-left-tab active>
        <template #icon>
          <home-icon />
        </template>
        <template #name> Home </template>
      </sidebar-left-tab>

      <sidebar-left-tab>
        <template #icon>
          <hashtag-icon />
        </template>
        <template #name> Explore </template>
      </sidebar-left-tab>

      <sidebar-left-tab>
        <template #icon>
          <bell-icon />
        </template>
        <template #name> Notifications </template>
      </sidebar-left-tab>

      <sidebar-left-tab>
        <template #icon>
          <inbox-icon />
        </template>
        <template #name> Messages </template>
      </sidebar-left-tab>

      <sidebar-left-tab>
        <template #icon>
          <bookmark-icon />
        </template>
        <template #name> Bookmarks </template>
      </sidebar-left-tab>
      <sidebar-left-tab>
        <template #icon>
          <document-text-icon />
        </template>
        <template #name> Lists </template>
      </sidebar-left-tab>

      <sidebar-left-tab>
        <template #icon>
          <user-icon />
        </template>
        <template #name> Profile </template>
      </sidebar-left-tab>

      <sidebar-left-tab>
        <template #icon>
          <information-circle-icon />
        </template>
        <template #name> More </template>
      </sidebar-left-tab>
    </div>
  </div>
</template>

<style scoped></style>
