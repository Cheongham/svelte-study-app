<script>
	import Router from "svelte-spa-router";
	import routes from "./route.js";
</script>

<!-- #1 svelte-spa-router -->

<nav class="nav1">  
	<a href="/#/">Home</a>
	<a href="/#/about">About</a>
</nav>

<Router {routes} />


<style> </style>