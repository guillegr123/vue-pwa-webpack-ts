<template>
  <v-ons-page>
    <v-ons-toolbar modifier="transparent"></v-ons-toolbar>
    <div class="header">
      <img src="../assets/onsenui-logo.png" alt="onsenui-logo">
    </div>

    <v-ons-list-title>Internal links</v-ons-list-title>
    <v-ons-list>
      <v-ons-list-item modifier="chevron" v-for="item in internalLinks" @click="goToInternal(item.link)" :key="item.link">
        <div class="left"><v-ons-icon fixed-width :icon="item.icon"></v-ons-icon></div>
        <div class="center">\{{ item.label }}</div>
      </v-ons-list-item>
    </v-ons-list>

    <v-ons-list-title>Onsen UI Essential Links</v-ons-list-title>
    <v-ons-list>
      <v-ons-list-item modifier="chevron" v-for="item in essentialLinks" @click="goTo(item.link)" :key="item.link">
        <div class="left"><v-ons-icon fixed-width :icon="item.icon"></v-ons-icon></div>
        <div class="center">\{{ item.label }}</div>
      </v-ons-list-item>
    </v-ons-list>
  </v-ons-page>
</template>

<script lang="ts">
import Vue from 'vue'{{#if_eq lintConfig "airbnb"}};{{/if_eq}}

const Component = Vue.extend({
  name: 'menu',
  data{{#unless_eq lintConfig "airbnb"}} {{/unless_eq}}() {
    return {
      essentialLinks: [
        {
          label: 'Docs',
          link: 'https://onsen.io/v2/docs/guide/vue/',
          icon: 'fa-book'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Gitter Chat',
          link: 'https://gitter.im/OnsenUI/OnsenUI',
          icon: 'fa-commenting'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Forum',
          link: 'https://community.onsen.io',
          icon: 'fa-comments'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Twitter',
          link: 'https://twitter.com/Onsen_UI',
          icon: 'fa-twitter'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Playground',
          link: 'https://tutorial.onsen.io/',
          icon: 'fa-graduation-cap'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
      ],
      internalLinks: [
        {
          label: 'Home',
          link: '/',
          icon: 'fa-book'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Movies',
          link: '/movies',
          icon: 'fa-commenting'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
      ]{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
    }{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
  },
  methods: {
    goTo{{#unless_eq lintConfig "airbnb"}} {{/unless_eq}}(url) {
      const newWindow = window.open(url, '_blank'){{#if_eq lintConfig "airbnb"}};{{/if_eq}}
      newWindow.opener = null{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
      newWindow.location = url{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
    },
    goToInternal{{#unless_eq lintConfig "airbnb"}} {{/unless_eq}}(path) {
      this.$router.replace(path){{#if_eq lintConfig "airbnb"}};{{/if_eq}}
    }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
  }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
}){{#if_eq lintConfig "airbnb"}};{{/if_eq}}

export default Component{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  text-align: center;
  margin-bottom: 20px;
}

img {
  max-width: 150px;
}

ons-list-title {
  text-transform: none;
}

ons-list-item {
  cursor: pointer;
}
</style>
