<template>
	<v-container>
		<v-layout text-center wrap>
			<v-flex >
				<v-img
					:src="require('../assets/logo.svg')"
					class="my-3"
					contain
					height="200"
				></v-img>
			
				<v-progress-circular indeterminate :color="colorFirst" :size="size" :width="width" style="margin-top:75px;">
					<v-progress-circular indeterminate :color="color" :size="calculatedSize" :width="width" >{{ text }}</v-progress-circular>
				</v-progress-circular>				
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>
export default {
	data: () => ({
		text: "",
		size: 100,
		width: 5,
		colorFirst: "primary",
		color: "cyan darken-1",
		ecosystem: [
			{
				text: 'vuetify-loader',
				href: 'https://github.com/vuetifyjs/vuetify-loader'
			},
			{
				text: 'github',
				href: 'https://github.com/vuetifyjs/vuetify'
			},
			{
				text: 'awesome-vuetify',
				href: 'https://github.com/vuetifyjs/awesome-vuetify'
			}
		],
		importantLinks: [
			{
				text: 'Documentation',
				href: 'https://vuetifyjs.com'
			},
			{
				text: 'Chat',
				href: 'https://community.vuetifyjs.com'
			},
			{
				text: 'Made with Vuetify',
				href: 'https://madewithvuejs.com/vuetify'
			},
			{
				text: 'Twitter',
				href: 'https://twitter.com/vuetifyjs'
			},
			{
				text: 'Articles',
				href: 'https://medium.com/vuetify'
			}
		],
		whatsNext: [
			{
				text: 'Explore components',
				href: 'https://vuetifyjs.com/components/api-explorer'
			},
			{
				text: 'Select a layout',
				href: 'https://vuetifyjs.com/layout/pre-defined'
			},
			{
				text: 'Frequently Asked Questions',
				href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions'
			}
		]
	}),
	created() {
		setTimeout(() => {
			this.text = "It will be endless";						
			setTimeout(() => {
			this.text = "What are u still looking for?";
			this.size += 200;
			this.width += 10;
			this.color = "deep-orange lighten-1";
			this.colorFirst = "orange accent-2";	
			this.$vuetify.theme.currentTheme.primary = '#eb7134';
			setTimeout(() => {
				this.text = "Ok lets go!";
				setTimeout(() => {
					this.$vuetify.theme.currentTheme.primary = '#1976D1';
					this.$router.push({ name: 'login'});
				}, 2000);
				
			}, 5000);		
			}, 10000);
		}, 5000);
	},
	computed:{
		calculatedSize() {
			return (this.size/100 * 90);
		}
	}

}
</script>
