<script>
import jobs from '~/content/jobs.js';

  export default {

  	computed: {
  		selectJob() {
  			let self = this;
  			return this.jobs.groups.find((job) => {
  				return job.jobid === self.jobid;
  			});
  		}
  	},

    data () {
    	return {
    		jobs:jobs
    	}
    },

    asyncData (context) {
    	return { "jobid": context.route.params.id }
    }
  }

</script>


<template>
	<section class="container">
		<h1>{{selectJob['title']}}</h1>
  		<h2>{{selectJob['company']}}</h2>
  		<p v-html="selectJob['description']"></p>
	</section>
</template>

<style>
</style>
