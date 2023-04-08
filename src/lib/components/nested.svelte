<script>
   import {onMount} from 'svelte';
   let VideoPlayer
   onMount(() => {
      if (typeof window !== 'undefined') {
         VideoPlayer = require('svelte-video-player');
      }
   });
</script>

<p>This is Paragraph</p>
<svelte:component this={VideoPlayer}>
   
</svelte:component>