<template>
	<div>
		<div class="container">
			<Hero />
			<LargeCardDisplay
				v-for="cardInfo in largeCardInfo"
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
import Nav from "@/components/fire/Nav"
import Hero from "@/components/fire/Hero"
import LargeCardDisplay from "@/components/fire/LargeCardDisplay"
import SmallCardDisplay from "@/components/fire/SmallCardDisplay"
import { largeCardSections, smallCardSections } from "@/assets/data.js"
export default {
	components: { Nav, Hero, LargeCardDisplay, SmallCardDisplay },
	data() {
		return {
			largeCardInfo: largeCardSections,
			smallCardSections
		}
	},
    layout: 'fire'
}
</script>
