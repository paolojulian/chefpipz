<template>
  <div class="home">
    <CCard>
      <div class="profile-picture">
      </div>
      <div class="profile-details">
        <div class="name">Paolo Vincent M. Julian</div>
        <div class="profile-title">I am a programmer</div>
        <div class="profile-description">
          Hi, I am a Software Application Developer.
          I also have a lot of hobbies. I love cooking good food from different cuisines. I also love playing computer games with my friends, I love singing and playing the guitar to my loved ones, I also love playing basketball and hiking and
          more importantly, I LOVE programming.
        </div>
      </div>
    </CCard>
    <CCard>
      <div class="principles">
        <div class="principle-item" v-for="principle in principles"
          :key="principle.name"
        >
          <div class="principle-name">{{ principle.name }}</div>
          <div class="principle-description">{{ principle.description }}</div>
        </div>
      </div>
    </CCard>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import CCard from '@/components/widgets/CCard.vue'

@Component({
  components: {
    CCard
  }
})
export default class Home extends Vue {
  private principles: Array<object> = [
    {
      name: 'Simple',
      description: 'Keeping functions and design as simple as possible.'
    },
    {
      name: 'Organized',
      description: 'One step at a time, do not overthink.'
    },
    {
      name: 'Clean',
      description: 'Codes should be neat and readable. It should be like telling a story.'
    },
    {
      name: 'Kind',
      description: 'Kindness always paves off. Keep your team intact, and also with your clients.'
    }
  ];
}
</script>

<style scoped>
.home {
  margin-top: 4px;
}
.profile-picture {
  height: 120px;
  width: 120px;
  margin: 12px auto 24px auto;
  background-color: #777777;
  border-radius: 50%;
}
.name {
  font-size: 20px;
}
.principles {
  text-align: left;
}
.principle-item {
  margin: 8px 0;
}
.principle-name {
  font-size: 24px;
  text-transform: uppercase;
  text-shadow: 0 2px 5px hsla(0,0%,0%,.25)
}
</style>
