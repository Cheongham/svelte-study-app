<script>
import {Router,Link,Route} from "svelte-routing";
import Home from "./routes/home.svelte";
import About from "./routes/about.svelte";
import Bind from "./routes/Bind.svelte";
import Lifecycle from "./routes/Lifecycle.svelte";
import Apis from "./routes/Apis.svelte";

export let url = "";
</script>

<Router {url}>
	<nav class="nav1">  
		<Link to="/">홈</Link>
		<Link to="about">..대하여</Link>
		<Link to="binding">데이터바인딩</Link>
		<Link to="lifecycle">라이프사이클</Link>
		<Link to="apis">APIs예제</Link>
	</nav>
	<div>
		<Route path="/"><Home /></Route>
		<Route path="about"><About /> </Route> 
		<Route path="binding" component={Bind} />
		<Route path="lifecycle" component={Lifecycle} />
		<Route path="apis"><Apis /></Route>
	</div>
</Router>

<style></style>