<template>
	<v-app>
		<v-app-bar color="red darken-4" dark app hide-on-scroll>
			<v-card
				style="width:100vw"
				class="d-flex justify-space-between align-center text-h4"
				color="transparent"
				flat
			>
				<v-menu offset-y>
					<template v-slot:activator="{ on, attrs }">
						<v-btn icon v-bind="attrs" v-on="on">
							<v-icon>mdi-menu</v-icon>
						</v-btn>
					</template>
					<v-list>
						<v-list-item class="pa-0">
							<v-btn href="https://rhindorop.github.io/PD180/" text>180</v-btn>
						</v-list-item>
						<v-list-item class="pa-0">
							<v-btn href="https://rhindorop.github.io/PD183/" text>183</v-btn>
						</v-list-item>
					</v-list>
				</v-menu>

				<div class="d-flex">
					<div class="d-none d-sm-flex mr-2">Peerless Dad</div>
					<div class="d-flex d-sm-none mr-2">PD</div>183
				</div>
				<v-btn @click="switchimg()" :color="num ? 'blue darken-1' : 'green darken-1'">{{curimg}}</v-btn>
			</v-card>
		</v-app-bar>

		<v-main>
			<Story :num="num"/>
		</v-main>
	</v-app>
</template>

<script>
import Story from "./components/Story";

export default {
	name: "App",
	components: { Story },
	data: () => ({
		num: 1,
		curimg: "MTL",
	}),
	methods: {
		switchimg() {
			if (this.num == 1) {
				this.num = 0;
				this.curimg = "RAW";
			} else {
				this.num = 1;
				this.curimg = "MTL";
			}
		},
	},
};
</script>
