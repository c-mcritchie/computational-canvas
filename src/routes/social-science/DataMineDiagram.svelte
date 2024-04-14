<script>
    export let steps = [
        {
            title: "Data Collection",
            items: ["Location", "Keyword", "Hashtag", "Profile"],
        },
        {
            title: "Elements of a Tweet",
            items: [
                "Account Details",
                "Post Text",
                "Images",
                "Videos",
                "Location",
                "Timestamp",
                "Post Interactions",
            ],
        },
        {
            title: "Filtering",
            items: [
                "Account Details",
                "Text Content",
                "Visual Content",
                "Location",
                "Timestamp",
                "Post Interactions",
            ],
        },
        {
            title: "Resulting Dataset",
            items: ["Analysis", "Manual", "Algorithms", "Neural Networks", "Hotspot"],
        },
        {
            title: "Resulting Data",
            items: [
                "Visualization",
                "Word Cloud",
                "Diagram",
                "Chart",
                "Graph",
                "Map",
                "Collage",
            ],
        },
    ];
</script>

<style>
    .arrow {
        border: solid transparent;
        border-width: 0.25rem 0.25rem 0 0.25rem;
        border-color: #4a5568 transparent transparent transparent;
        display: inline-block;
        margin-top: 0.5rem;
    }
</style>
<div class="card p-4">
    <div class="flex justify-center">
        {#each steps as step, i}
            <div class="flex flex-col items-start justify-items-start mx-4">
                <h2 class="font-semibold text-lg mb-4 self-start">{step.title}</h2>
                {#each step.items as item, j}
                    <p class="ml-2 {(j !== step.items.length - 1) ? 'border-b-2 pb-1' : ''}">{item}</p>
                {/each}
            </div>
            <div class="flex flex-col items-center justify-center mx-4">
                {#if i !== steps.length - 1}
                    <div class="arrow transform -rotate-90"></div>
                {/if}
            </div>
        {/each}
    </div>
</div>
