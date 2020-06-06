<template>
  <div id="nav">
    <div class="logo">PIPZ</div>
    <div class="links">
      <router-link v-for="{ name, link, icon } in navigationList"
        :key="name"
        :to="link">
          <span class="name">{{ name }}</span>
          <span class="icon">{{ icon }}</span>
      </router-link>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

interface Link {
  name: string;
  link: string;
  icon: string;
}

@Component
export default class Navbar extends Vue {
  private navigationList: Array<Link> = [
    {
      name: 'Home',
      link: '/',
      icon: 'Home'
    },
    {
      name: 'Music',
      link: '/',
      icon: 'Music'
    },
    {
      name: 'Recipes',
      link: '/',
      icon: 'Recipes'
    },
    {
      name: 'Portfolio',
      link: '/about',
      icon: 'Portfolio'
    }
  ];
}
</script>

<style scoped>
#nav {
  position: fixed;
  bottom: 0;
  left: 0;
  background-color: var(--orange);
  width: 100%;
  height: 50px;
  margin: auto 0;
}

.logo {
  display: none;
}

.links {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.links a {
  height: 100%;
  width: 100%;
  margin: 0 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

#nav a .name {
  display: none;
}

#nav a {
  font-weight: bold;
  color: var(--light-default);
}

#nav a.router-link-exact-active {
  color: var(--light-default);
}

@media only screen and (min-width: 768px) {
  #nav {
    top: 0;
    bottom: unset;
    left: 0;
    padding: 0 150px;
    clear: both;
  }

  .logo {
    display: flex;
    align-items: center;
    font-size: 24px;
    float: left;
    height: 100%;
  }
  .links {
    float: right;
  }

  #nav a .icon {
    display: block;
  }

  #nav a .name {
    display: none;
  }
}
</style>
