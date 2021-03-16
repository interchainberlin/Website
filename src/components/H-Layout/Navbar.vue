<template>
  <div :class='NavbarContainer'>
    <div :class='IGNav'>
      <div :class='IGContainer'>
        <div :class='Container'>
          <img :class='Icon' src='../../assets/Logo.svg'/>
          <p :class='header'>Interchain GmbH</p>
        </div>
        <div :class='Container'>
          <p :class='subheader'>Team</p>
          <a href='https://github.com/interchainberlin' target='_blank' >
            <img :class='Icon' src='../../assets/GithubGray.png'/>
          </a>
          <a href='https://interchain-io.medium.com' target='_blank' >
            <img :class='Icon' src='../../assets/Medium_logo.svg.png'/>
          </a>
          <Button title='We are hiring' url='https://interchain-gmbh.breezy.hr/'/>
        </div>
      </div>
    </div>

    <div :class='ICFBanner'>
      <div :class='ICFContainer'>
      <p :class='subheader'>Interchain Foundation Our Grant Program →</p>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api';
import Button from './Button.vue'; 

export default defineComponent({
  name: 'Navbar',
  components: {
    Button,
  },
  data() {
    return {
      NavbarContainer: 'w-full fixed top-0 z-50',
      header: 'text-white text-lg',
      subheader: 'text-white text-sm',

      IGNav: 'bg-gray-800',
      IGContainer: 'xl:container xl:mx-auto p-2 flex flex-wrap justify-between items-center',
      Container: 'flex flex-wrap items-center space-x-6',
      Icon: 'w-7 rounded-full', 
      ICFBanner: 'bg-black',
      ICFContainer: 'xl:container xl:mx-auto p-2',


    }
  }
})
</script>