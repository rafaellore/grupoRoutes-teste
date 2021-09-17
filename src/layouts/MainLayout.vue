<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="" style="background-color: #c32442;">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>
          <q-icon name="question_answer" class="white" style="font-size: 28px; cursor: pointer;" />
          <q-icon name="help_outline" class="white" style="font-size: 28px; padding: 0 20px; cursor: pointer;" />
        </div>
        <div style="border-left: 1px solid #232323;"><q-icon name="account_circle" class="white" style="font-size: 28px; padding: 0 20px; cursor: pointer;" /></div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Essential Links
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Dashboard',
    icon: 'dashboard',
  },
  {
    title: 'Exemplo 1',
    icon: 'volunteer_activism',
  },
  {
    title: 'Exemplo 2',
    icon: 'place',
  },
  {
    title: 'Exemplo 3',
    icon: 'point_of_sale',
  },
  {
    title: 'Exemplo 4',
    icon: 'edit',
  },
  {
    title: 'Exemplo 5',
    icon: 'settings',
  }
];

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
