<script>
	import { fade, blur, fly, slide, scale, draw, crossfade } from 'svelte/transition';
	let condition = false;
	let visible = true;
</script>

<svelte:head>
	<title>FYNX</title>
</svelte:head>

{#if visible}
	<div class="box" transition:scale>Fades in and out</div>
{/if}

<label>
	<input type="checkbox" bind:checked={visible} />
	visible
</label>

<br /><br />
컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠
나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는
영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠
나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는 영역 컨텐츠 나오는
영역
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
컨텐츠 나오는 영역

<style>
	.box {
		border: solid #666 1px;
		padding: 10px;
	}
</style>
