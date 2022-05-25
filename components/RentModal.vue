<template>
  <div>
    <b-button id="show-btn" @click="showModal">Rent</b-button>
  
    <b-modal ref="my-modal" hide-footer title="Using Component Methods">
      <div class="calendar-container">
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Nostrum praesentium facilis magnam alias consectetur quas dicta voluptatum distinctio dignissimos eius commodi aut ratione in, odio voluptatem. Repellat commodi suscipit quo quis autem ipsam, recusandae repudiandae velit ab quaerat molestias fugiat.</p>
        <vc-calendar
          :value="null"
            color="red"
            is-dark
            is-range
  />      
      </div>
      <b-button id="show-btn" variant="outline-danger" @click="()=>{
        addItem(product.id)
        hideModal()
        }">
        Rent
        </b-button>
    </b-modal>
  </div>
</template>

<script>
import {mapMutations} from "vuex"
  export default {
    props:['product'],
    methods: {
      showModal() {
        this.$refs['my-modal'].show()
      },
      hideModal() {
        this.$refs['my-modal'].hide()
      },
      toggleModal() {
        // We pass the ID of the button that we want to return focus to
        // when the modal has hidden
        this.$refs['my-modal'].toggle('#toggle-btn')
      },
      ...mapMutations(['addItem'])
    }
  }
</script>

<style scoped>
    button {
        width: 100%;
        border: none;
        padding: 0.5rem;
        color: white;
        font-weight: 700;
        padding: 1rem 4rem;
        border-radius: 100rem;
        background-color: rgb(231, 81, 43);
        color: white;
        font-weight: 700;
        transition: 0.5s;
    }
    .calendar-container {
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
    }
    p {
      color: grey
    }
    .text-container {
      padding: 0.5rem
    }
</style>