<script>
	import AccountCircle from "svelte-material-icons/AccountCircle.svelte";
</script>

<header>
	<div class="user-box">
		<AccountCircle size="2.5rem" color="#fff" />
		<span class="mb_name">회원명</span>
	</div>
	<div class="corner">

	</div>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		position:sticky;top:0px;width:100%;height:50px;
		background: var(--header-color);
		box-shadow: 0px 1px 5px 0px  rgb(55, 55, 55);
		z-index:50;
	} /**background: rgb(73, 73, 245);*/
	.user-box {display:flex;align-items: center;padding-left:15px;height:100%;}
	.mb_name {margin-left:5px;font-size:1.25rem;}
	.corner {}
</style>
