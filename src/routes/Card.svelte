<script>
    import { Button, Card } from "flowbite-svelte";
    let {title, description} = $props();
</script>
<div class="flex flex-col">
    <Card img="/images/image-1.webp">
        <div class="m-6">
            <h5
                class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white"
            >
                {title}
            </h5>
            <p
                class="mb-3 leading-tight font-normal text-gray-700 dark:text-gray-400"
            >
                {description}
            </p>
            <Button class="w-40" color="blue">
                Read more
            </Button>
        </div>
    </Card>
</div>