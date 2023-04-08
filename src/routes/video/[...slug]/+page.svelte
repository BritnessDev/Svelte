<script context="module" lang="ts">
  export const prerender = true;
</script>

<script lang="ts">
  // this prevents the custom elements from being redefined when the REPL is updated and reloads, which throws an error
  // this means that any changes to the custom element won't be picked up without saving and refreshing the REPL
  // const oldRegister = customElements.define;
  // customElements.define = function(name, constructor, options) {
  // 	if (!customElements.get(name)) {
  // 		oldRegister(name, constructor, options);
  // 	}
  // }
  // import { page } from '$app/stores';
  import { onMount } from "svelte";
  onMount(async () => {
    await import("@mux/mux-player");
    const videoContext = document.querySelector("mux-video video");
    videoContext.setAttribute("autoplay", "autoplay");
    videoContext.setAttribute("autoload", "true");
    videoContext.setAttribute("playsinline", "true");
    videoContext.autoplay = "autoplay";
    videoContext.autoload = true;
    videoContext.playsinline = true;
    videoContext.play();
    // const video = document.getElementById('video-id-54321');
    
    // video.play().then(function () {
    //   // autoplay was successful!
    //   console.log("111111111111111")
    // }).catch(function (error) {
    //   // do something if you want to handle or track this error
    //   console.log("22222222222222222222", error);
    // });
  });
</script>

<div>
    <mux-player
    metadata-video-id="video-id-54321"
    metadata-video-title="Svelte Kit: Episode 2"
    metadata-viewer-user-id="user-id-sveltekit007"
    stream-type="on-demand"
    src="https://media-files.vidstack.io/hls/index.m3u8"
    autoplay={true}
    autoload={true}
    playsinline={true}
  />
</div>
