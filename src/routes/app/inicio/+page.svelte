<script>
	import { onMount } from "svelte";
	import Timeline from "$lib/components/TimeLine/Timeline.svelte";
	
	let data;
	const API = "https://api.thecatapi.com/v1/";
	const API_KEY = import.meta.env.VITE_API_KEY;

	onMount(async()=>{
		const response = await fetch(`${API}images/search?size=full&page=0&limit=10&mime_types=jpg&has_breeds=true&format=json`, {
			method: "GET",
			headers: {
				"Content-Type": "application/json",
				"x-api-key": API_KEY
			}
		}
		);
		data = await response.json();
	})


</script>
<svelte:head>
	<title>Catstagram | Home</title>
</svelte:head>
<div class="home">
	<Timeline data = {data}/>
</div>