<template>
    <div>
        <div class="container">
            <LargeCardDisplay
                v-for="cardInfo in largeCardInfo.slice(0.1)"
                :key="cardInfo.id"
                :cardsSection="cardInfo"
            />
            <SmallCardDisplay
                v-for="cardInfo in smallCardSections"
                :key="cardInfo.id"
                :cardsSection="cardInfo"
            />
        </div>
    </div>
</template>

<script>
    import LargeCardDisplay from "@/components/LargeCardDisplay"
    import SmallCardDisplay from "@/components/SmallCardDisplay"
    import { largeCardSections, smallCardSections } from "@/assets/data.js"
    export default {
        components: { LargeCardDisplay, SmallCardDisplay },
        data() {
            return {
                largeCardInfo: largeCardSections,
                smallCardSections: smallCardSections,
            }
        }
    }
</script>

<style scoped>

</style>