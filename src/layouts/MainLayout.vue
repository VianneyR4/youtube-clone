<template>
  <q-layout view="hHh Lpr lff">
    <!-- Header Starts -->
    <q-header class="header">
      <div class="header__left">
        <i id="menu" class="material-icons" @click="toggleLeftDrawer">menu</i>
        <img
          src="../assets/cdnlogo.com_youtube-icon.svg"
          alt="ytb"
          height="25px"
        />
      </div>

      <div class="header__search">
        <form action="">
          <input type="text" placeholder="Search" />
          <button><i class="material-icons">search</i></button>
        </form>
      </div>

      <div class="header__icons">
        <i class="material-icons display-this">search</i>
        <i class="material-icons">videocam</i>
        <i class="material-icons">apps</i>
        <i class="material-icons">notifications</i>
        <i class="material-icons display-this">account_circle</i>
      </div>
    </q-header>
    <!-- Header Ends -->

    <!-- Sidebar Starts -->
    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      :width="100"
      class="sidebar"
    >
      <!-- <q-list>
        <q-item-label header> Essential Links </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list> -->

      <div class="sidebar__categories">
        <div class="sidebar__category active">
          <i class="material-icons">home</i>
          <span>Home</span>
        </div>
        <div class="sidebar__category">
          <i class="material-icons">local_fire_department</i>
          <span>Trending</span>
        </div>
        <div class="sidebar__category">
          <i class="material-icons">subscriptions</i>
          <span>Subcriptions</span>
        </div>
      </div>
      <hr />
      <div class="sidebar__categories">
        <div class="sidebar__category">
          <i class="material-icons">library_add_check</i>
          <span>Library</span>
        </div>
        <div class="sidebar__category">
          <i class="material-icons">history</i>
          <span>History</span>
        </div>
        <div class="sidebar__category">
          <i class="material-icons">play_arrow</i>
          <span>Your Videos</span>
        </div>
        <div class="sidebar__category">
          <i class="material-icons">watch_later</i>
          <span>Watch Later</span>
        </div>
        <div class="sidebar__category">
          <i class="material-icons">thumb_up</i>
          <span>Liked Videos</span>
        </div>
      </div>
      <hr />
    </q-drawer>
    <!-- Sidebar Ends -->

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

defineOptions({
  name: "MainLayout",
});

const linksList = [
  {
    title: "Docs",
    caption: "quasar.dev",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "Github",
    caption: "github.com/quasarframework",
    icon: "code",
    link: "https://github.com/quasarframework",
  },
  {
    title: "Discord Chat Channel",
    caption: "chat.quasar.dev",
    icon: "chat",
    link: "https://chat.quasar.dev",
  },
  {
    title: "Forum",
    caption: "forum.quasar.dev",
    icon: "record_voice_over",
    link: "https://forum.quasar.dev",
  },
  {
    title: "Twitter",
    caption: "@quasarframework",
    icon: "rss_feed",
    link: "https://twitter.quasar.dev",
  },
  {
    title: "Facebook",
    caption: "@QuasarFramework",
    icon: "public",
    link: "https://facebook.quasar.dev",
  },
  {
    title: "Quasar Awesome",
    caption: "Community Quasar projects",
    icon: "favorite",
    link: "https://awesome.quasar.dev",
  },
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>

<style>
@import "../css/style.css";
</style>
