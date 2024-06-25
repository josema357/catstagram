<script>
	import { afterUpdate, onMount } from "svelte";
	import Timeline from "$lib/components/TimeLine/Timeline.svelte";
	import Loader from "$lib/components/Loader/Loader.svelte"
	
	let data=[];
	let page = 0;
	let limit = 10;
	const API = "https://api.thecatapi.com/v1/";
	const API_KEY = import.meta.env.VITE_API_KEY;
	let observer;
	let targetRef;

	onMount(async()=>{
		loadMoreData();
		observer = new IntersectionObserver(handleObserver, {threshold: 0.5});
		observer.observe(targetRef);
	})
	async function loadMoreData() {
    const response = await fetch(`${API}images/search?size=full&page=${page}&limit=${limit}&mime_types=jpg&has_breeds=true&format=json`, {
      method: "GET",
      headers: {
        "Content-Type": "application/json",
        "x-api-key": API_KEY
      }
    });
    const newData = await response.json();
    data = [...data, ...newData];
    page++;
  }
	function handleObserver(entries) {
    if (entries[0].isIntersecting) {
      loadMoreData();
    }
  }

	afterUpdate(() => {
    observer.disconnect();
    observer.observe(targetRef); 
		console.log(data)
  });

</script>
<svelte:head>
	<title>Catstagram | Home</title>
</svelte:head>
<div class="home">
	<Timeline data = {data}>
		<div bind:this={targetRef}>
			<Loader/>
		</div>
	</Timeline>
	
</div>