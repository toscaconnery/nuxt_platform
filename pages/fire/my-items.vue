<template>
    <div>
        <div class="container">
            <MyItem 
                v-for="item in myRentals"
                :key="item.id"
                :item="item"
            />
        </div>
    </div>
</template>

<script>
    import { mapState } from "vuex"
    import MyItem from "@/components/fire/MyItem"
    export default {
        components: { MyItem },
        layout: 'no-nav-fire',
        computed: {
            ...mapState(['myRentals'])
        },
        created() {
            console.log('> created')
            console.log(this.myRentals)
        }
    }
</script>

<style scoped>
</style>