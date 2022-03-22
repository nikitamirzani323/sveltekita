<script>
    import '../app.css';
    import FooterCustom from '$lib/components/Footer_custom.svelte';
</script>
<main class="container mx-auto">
    <header>NINJA NINJA</header>
    <slot></slot>
    <FooterCustom />
</main>