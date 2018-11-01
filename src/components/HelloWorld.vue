<template>
	<div class="hello" id="body">
	</div>
</template>

<script>
	import D3Relation from '@/components/d3-relation'

	export default {
		name: 'HelloWorld',
		data() {
			return {}
		},
		mounted() {
			this.InTerFace();
		},
		methods: {
		InTerFace:function(){		
				$.getJSON('static/data.json', function(data) {
					// let data = data;
					// console.log(data);
					// return;
					new D3Relation({
						nodes: data.nodes,
						links: data.links,
					})
				})
			}
		}
	}
</script>
<style scoped>
	.tooltip {
		position: fixed;
		display: block;
		padding: .4rem;
		border-radius: .25rem;
		background-color: rgba(0, 0, 0, .8);
		white-space: nowrap;
		color: #fff;
		font-size: .8rem;
	}

	.tooltip a {
		color: #658ccd;
		cursor: pointer;
		-webkit-tap-highlight-color: transparent;
	}
</style>
