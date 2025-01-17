<script>
	import '../app.css';
	let { children } = $props();
</script>

<div class="gradient flex min-h-screen flex-col items-center justify-between p-8">
	{@render children()}
</div>
