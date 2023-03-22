<script lang="ts">
  import { ImageStatus } from "../types.d";
  import StepEdit from "./StepEdit.svelte";
  import StepUpload from "./StepUpload.svelte";
  import { imageStatus } from "./store.js";
</script>

<div
  class="maz-w-xl m-auto grid grid-cols-1 place-content-center w-full h-screen p-4"
>
  <header class="flex justify-center py-10">
    <h1 class="text-3xl font-bold text-green-900 tracking-tighter">
      Remove<span class="text-blue-600">Bg</span>
    </h1>
  </header>

  <main class="w-full block">
  {#if $imageStatus === ImageStatus.READY ||$imageStatus === ImageStatus.UPLOADING}
    <StepUpload />
    {:else if $imageStatus === ImageStatus.DONE}
    <StepEdit />
  {/if}
  </main>
</div>
