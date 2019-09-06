<script>
	export default {
		onLaunch: function() {
			// #ifdef APP-PLUS
			if(process.env.NODE_ENV === 'development'){
			    uni.setKeepScreenOn({
			        keepScreenOn: true
			    });
			}
			// #endif
		},
		onShow: function() {
			
		},
		onHide: function() {
			
		}
	}
</script>

<style>
	@import url("/components/gaoyia-parse/parse.css");
</style>
