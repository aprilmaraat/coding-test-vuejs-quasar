<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="q-gutter-md q-py-sm">

        <q-toolbar-title>
          Contacts
        </q-toolbar-title>

        <q-separator vertical/>

        <q-input color="grey-3" outlined v-model="searchText" label="Search" dense>
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>

        <q-space />

        <q-btn class="bg-grey-3" style="color: blue" label="Add Contact" />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <EssentialLink
          v-for="link in mainLinks"
          :key="link.title"
          v-bind="link"
        />

        <q-item-label
          header
        >
          Custom
        </q-item-label>

        <EssentialLink
          v-for="link in customLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>

      <q-list>
        <q-item-label
          header
        >
          Feature
        </q-item-label>

        <EssentialLink
          v-for="link in featuredLinks"
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

const mainLinkList = [
  {
    title: 'Dashboard',
    caption: '',
    icon: 'grid_view',
    link: ''
  }
];

const customLinkList = [
  {
    title: 'Employee',
    caption: '',
    icon: 'grid_view',
    link: ''
  },
  {
    title: 'Calendar',
    caption: '',
    icon: 'date_range',
    link: ''
  }
];

const featuredLinkList = [
  {
    title: 'Subcontractor',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },{
    title: 'Supplier',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },
  {
    title: 'Users',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },
  {
    title: 'File Upload',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },
  {
    title: 'Widgets',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },
  {
    title: 'Calendar',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },
  {
    title: 'Charts',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },
  {
    title: 'Maps',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },
  {
    title: 'Miscellaneous',
    caption: '',
    icon: 'grid_view',
    link: 'https://quasar.dev'
  },
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
      mainLinks: mainLinkList,
      customLinks: customLinkList,
      featuredLinks: featuredLinkList,
      leftDrawerOpen: true,
      searchText: '',
    }
  }
})
</script>
