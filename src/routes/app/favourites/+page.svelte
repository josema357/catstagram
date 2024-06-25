<script>
  import { onMount } from "svelte";
  import Timeline from "$lib/components/TimeLine/Timeline.svelte";

  let data=[];
  const API = "https://api.thecatapi.com/v1/";
	const API_KEY = import.meta.env.VITE_API_KEY;
  let favourites=[];

  onMount(async()=>{
		const response = await fetch(`${API}favourites`, {
      method: "GET",
      headers: {
        "Content-Type": "application/json",
        "x-api-key": API_KEY
      }
    })
      .then((res) => res.json());
    data = response;
    data.map(async(cat)=>{
    const response = await fetch(`${API}images/${cat.image_id}`, {
      method: "GET",
      headers: {
        "Content-Type": "application/json",
        "x-api-key": API_KEY
      }
    })
      .then((res) => res.json());
    favourites = [...favourites, response]
    })
	})

  

  

</script>

<div class="favourites">
  <Timeline data={favourites}>
    
  </Timeline>
</div>