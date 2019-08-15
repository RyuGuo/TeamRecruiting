<template>
	<div class="container">
		<ul class="arrow-wrap">
		  <li class="arrow arrow1"></li>
		  <li class="arrow arrow2"></li>
		  <li class="arrow arrow3"></li>
		</ul>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
}

.container {
  height: 40px;
  width: 40px;
}

.arrow-wrap {
  list-style: none;
  height: 100%;
  width: 100%;
}

.arrow {
  position: relative;
  display: block;
  height: 33.33%;
  width: 100%;
  background: #fff;
  animation: Pull-up-arrow-animate 2s ease-in-out infinite;
  clip-path: polygon(98% 17%, 100% 29%, 50% 100%, 0 29%, 2% 17%, 50% 85%);
}

.arrow1 {
  animation-delay: 0.1s;
}
.arrow2 {
  animation-delay: 0.5s;
}
.arrow3 {
  animation-delay: 0.9s;
}

@keyframes Pull-up-arrow-animate {
  0%{
    opacity: 1;
  }

  50%{
    opacity: 0.5;
  }
  100%{
    
    background: transparent;
  }
}
</style>
