<script context="module">
export async function load({fetch}) {
    const res = await fetch('https://jsonplaceholder.typicode.com/posts')
    const homes = await res.json()

    if(res.ok){
        return {
            props: {
                homes
            }
        }
    }
    return {
        status : res.status,
        error: new Error("Could not fetch the homes")
    }
}
</script>
<script>
    import Menu from '$lib/components/Menu.svelte';
    import Card from '$lib/components/Card.svelte';

    export let homes;
    let title = 'Ninja Gaming Guides'

    const updateTitle = () => {
        title = "something completely different"
    }
</script>
<div class="text-center m-20 uppercase">
    <h2 class="text-4xl">{title}</h2>
    <Menu />
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Magni voluptatum, suscipit explicabo est facilis tenetur placeat obcaecati accusamus dicta exercitationem rerum officiis. Vero delectus iure, unde aliquid veniam nesciunt impedit ducimus sunt eaque omnis. Dignissimos assumenda ipsam qui dicta quas deleniti maiores sit ullam commodi, id itaque! Ipsa quam mollitia voluptatem soluta quod sequi natus, consequuntur in? Perferendis, ad veritatis laborum totam ipsa quisquam voluptates laudantium explicabo adipisci placeat modi ut officiis aliquid labore eveniet debitis illum unde quod ab dolor. Ad facilis tenetur nulla ipsam recusandae reiciendis, ab qui corrupti mollitia exercitationem eos animi iste distinctio ut, a nihil non, tempora repellat excepturi fugiat inventore molestiae officia. Dignissimos fuga facere at, magni, neque enim quis assumenda corporis ea nobis cupiditate. Cupiditate odio autem saepe amet cumque, sint molestias harum incidunt dolor ad suscipit nulla quaerat ea assumenda quas illum molestiae in facilis deserunt totam natus repudiandae tempora praesentium. Explicabo quis repellendus optio itaque maiores blanditiis modi odio vel fugiat excepturi dignissimos animi provident a, ipsum cumque autem vitae perferendis? Cumque recusandae modi, culpa voluptatibus blanditiis corrupti unde quam esse vitae iusto quis saepe obcaecati fugit rerum adipisci fuga sequi perferendis debitis laborum provident eligendi. Itaque aut mollitia exercitationem aliquam.
    </p>
    <ul class="mt-4 mr">
        {#each homes as rec }
            <li class="text-left">
                <a class="border inline-block p-2 mt-2" href="#">{rec.title}</a>
            </li>
        {/each}
    </ul>
    <button class="btn rounded-sm" on:click="{updateTitle}">Change Title</button>
    <input 
    bind:value="{title}"
    type="text" 
    placeholder="Type here" 
    class="input w-full ml-5 max-w-xs rounded-none">
</div>

<Card>
    <p>
        Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation
    </p>
</Card>
