<template>
	<section class="splash">
		<div class="splash-container">
			<h1 class="splash__title">Junior Dev Jobs</h1>
	    	<p class="splash__subtitle">Find Your First Dev Job</p>			
		</div>
	</section>
</template>

<style>
	.splash {
		margin:0;
		padding:0;
		width:100%;
		height:200px;
		color:white;
		background: linear-gradient( rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.75) ), url("/images/splash.jpg");
		background-position: center;
  		background-repeat: no-repeat;
  		display:table;
	}

	.splash-container {
		display: table-cell;
		vertical-align: middle;
	}

	.splash__title {
		text-align: center;
	}

	.splash__subtitle {
		text-align: center;
	}

</style>