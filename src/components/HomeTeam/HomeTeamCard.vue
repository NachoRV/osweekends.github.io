<template>
  <div class="team-card">
    <div class="team-card__img-wrapper">
      <img
        :src="img"
        :alt="name"
        class="team-card__img">
    </div>
    <h3 class="team-card__name"> {{ name }} </h3>
    <p class="team-card__role"> {{ role }} </p>
    <div class="team-card__icons">
      <a
        v-if="github"
        :href="github"
        title="github"
        target="_blank"> <i class="fab fa-github team-card__icon" /></a>
      <a
        v-if="twitter"
        :href="twitter"
        title="twitter"
        target="_blank"><i class="fab fa-twitter team-card__icon" /></a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
      default: 'Fulanito'
    },
    role: {
      type: String,
      required: true,
      default: 'Guilder'
    },
    img: {
      type: String,
      required: true,
      default: '/v.png'
    },
    github: {
      type: String,
      required: false,
      default: ''
    },
    twitter: {
      type: String,
      required: false,
      default: ''
    }
  }
}
</script>

<style lang="stylus" scoped>
.team-card
  margin 10px 20px
  padding 25px
  text-align center
  color #121212

  &__img-wrapper
    width 200px
    height 200px
    border-radius 100%
    box-shadow 0 0 20px rgba(#000, .25);
    overflow hidden
    margin 0 auto
    transition all .5s

    &:hover
      box-shadow 0 0 30px rgba(#000, .35)

    &:hover > img
      transform scale(1.1)

  &__img
    width 100%
    transition all .5s

  &__name
    font-size 18px
    font-weight 600
    padding-top 10px

  &__role
    margin-bottom 5px

  &__icon
    font-size 20px
    margin 0 5px;
</style>
