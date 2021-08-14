<template>
	<v-container class="black" fluid pa-0>
		<v-sheet class="mx-auto" v-for="i in len" :key="i" max-width="750px" style="position:relative">
			<v-img :src="require('../assets/'+i+'.jpg')" eager style="z-index: 0"/>
			<v-img
				:src="require('../assets/'+i+'TL.png')"
				style="z-index: 1; position:absolute; top:0"
				v-if="num"
				eager
			/>
		</v-sheet>
	</v-container>
</template>

<script>
export default {
	name: "Story",
	props: [ "num" ],
	data: () => ({ len: 0 }),
	methods: {
		piclen() {
			const illustrations = require.context("../assets/", false, /^.*\.jpg$/);
			this.len = illustrations.keys().length;
		},
	},
	created() {
		this.piclen();
	},
};
</script>
