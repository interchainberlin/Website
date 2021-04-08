<template>
  <div :class='TeamContainer'>
     <h3 :class='subheader'> Meet Our Team </h3>
     <hr/>
     <br/>
     <!-- Map through teams from teams API -->
      <div :class='TeamList'>
        <div :class='Card' v-for='teamMember in teamMembers' :key='teamMember.id'> 
          
          <!-- <div :class='Card' v-for='teamMemberProfile in teamMember.Profile' :key='teamMemberProfile.id'> 
            <img :class='Profile' :src='teamMemberProfile.url'/>
          </div> -->
          <img :class='Profile' :src='teamMember.ProfileURL'/>

          <div :class='Info'>
            <p :class='body1'>{{teamMember.FirstName}} {{teamMember.LastName}}</p>
            <p :class='body2'>{{teamMember.Role}}</p>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api';

export default defineComponent({
  name: 'Team',
  props: {
    teamMembers: Object,
  },
  data() {
    return {
      TeamContainer: 'p-2 flex flex-col flex-wrap my-40 ',
      TeamList: 'grid grid-cols-2 md:grid-cols-3 gap-10 my-10 ',
      Card: 'hover:border hover:border-solid-blue flex flex-wrap space-y-5 md:space-y-0',
      Profile: 'bg-gray-50 w-28 h-28',
      Info: 'w-3/5 sm:pl-2 md:px-5',


      subheader: 'text-4xl',
      body1: 'font-bold',
      body2: 'font-light',
    }
  },
})
</script>