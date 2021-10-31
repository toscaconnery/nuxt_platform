<template>
    <div>
        <b-button id="show-btn" @click="showModal">Rent</b-button>
        <!-- <b-button id="toggle-btn" @click="toggleModal">Toggle Modal</b-button> -->

        <b-modal ref="my-modal" hide-footer title="Using Component Methods">
            <div class="calendar-container">
                <div class="text-container">
                    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Velit, harum in vero doloremque aperiam veniam accusantium neque rem ea labore earum itaque perspiciatis? Natus sint culpa distinctio molestias ab ratione aspernatur magnam ipsum, excepturi illo, reprehenderit, adipisci hic amet ea.</p>
                </div>
                <vc-date-picker 
                    :value="null"
                    color="red"
                    is-dark
                    is-range
                />
            </div>
            <b-button 
                id="show-btn" 
                variant="outline-danger" 
                @click="() => {
                    addItem(product.id)
                    hideModal()
                }"
            >
                Order
            </b-button>
            <!-- <div class="d-block text-center">
                <h3>Hello From My Modal!</h3>
            </div>
            <b-button class="mt-3" variant="outline-danger" block @click="hideModal">Close Me</b-button>
            <b-button class="mt-2" variant="outline-warning" block @click="toggleModal">Toggle Me</b-button> -->
        </b-modal>
    </div>
</template>

<script>
    // import vc-calendar from rom 'v-calendar'
    import { mapMutations } from "vuex"
    export default {
        props: ['product'],
        methods: {
            showModal() {
                this.$refs['my-modal'].show()
            },
            hideModal() {
                this.$refs['my-modal'].hide()
            },
            // toggleModal() {
            //     // We pass the ID of the button that we want to return focus to
            //     // when the modal has hidden
            //     this.$refs['my-modal'].toggle('#toggle-btn')
            // }
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