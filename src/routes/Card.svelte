<script>
    import { A, Button, Card, Modal, P } from "flowbite-svelte";
    let {title, description, briefDescription, link, imageLink} = $props();

    let visible = $state(false);

</script>

<Modal bind:open={visible} title={title} onaction={()=>{
    visible = !visible
}} >


<P>

    {description}
</P>


<A href={link} target="_blank"> Click to go to the project page</A>

</Modal>
<div class="flex flex-col">
    <Card img={imageLink}>
        <div class="m-6">
            <h5
                class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white"
            >
                {title}
            </h5>
            <p
                class="mb-3 leading-tight font-normal text-gray-700 dark:text-gray-400"
            >
                {briefDescription}
            </p>
            <Button class="w-40" color="blue" onclick={()=>{

                visible = true;
            }}>
                Read more
            </Button>
        </div>
    </Card>
</div>