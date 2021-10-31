<template>
    <div>
        <div class="container">
            <LargeCardDisplay
                v-for="cardInfo in largeCardInfo.slice(0.1)"
                :key="'lg-'+cardInfo.id"
                :cardsSection="cardInfo"
            />
            <SmallCardDisplay
                v-for="cardInfo in smallCardSections"
                :key="'sm-'+cardInfo.id"
                :cardsSection="cardInfo"
            />
        </div>
    </div>
</template>

<script>
    import LargeCardDisplay from "@/components/fire/LargeCardDisplay"
    import SmallCardDisplay from "@/components/fire/SmallCardDisplay"
    import { largeCardSections, smallCardSections } from "@/assets/data.js"
    export default {
        components: { LargeCardDisplay, SmallCardDisplay },
        data() {
            return {
                largeCardInfo: largeCardSections,
                smallCardSections: smallCardSections,
            }
        },
        layout: 'fire'
    }
</script>

<style scoped>

</style>