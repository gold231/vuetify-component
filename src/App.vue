<template>
  <v-app>
    <v-main>
      <ButtonComp :styles="{
        state: state[1],
        fill: fill_color[1],
        outline: outline_color[0],
        text: '1,000,000',
        text_size: 24,
        select: select[0],
        select_size: 16,
        oval: 300
      }" />
    </v-main>
  </v-app>
</template>

<script>
import ButtonComp from './components/ButtonComp';

export default {
  name: 'App',

  components: {
    ButtonComp,
  },

  data: () => ({
    state: [ "view", "edit" ],
    fill_color: [ "blue", "white", "red" ],
    outline_color: [ "default", "aligned", "misaligned" ],
    select: [ "per occurrence", "per claim", "per year" ]
  }),
};
</script>
