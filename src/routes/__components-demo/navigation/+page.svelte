<!-- Эта страница сделана только для тестового просмотра компонента Navigation -->

<script>
    import Navigation from '$lib/components/Navigation.svelte';
</script>

<div class="container mx-auto p-6">
    <h1 class="text-xl mb-4">Navigation component</h1>

    <div class="mb-8">
        <h2 class="text-xl mb-4">tall = true</h2>
        <Navigation tall={true} />
    </div>

    <div class="mb-8">
        <h2 class="text-xl mb-4">tall = false</h2>
        <Navigation tall={false} />
    </div>
</div>