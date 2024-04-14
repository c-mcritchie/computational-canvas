<script>
    import { onMount } from 'svelte';
    import anime from 'animejs';
    import { tweened } from 'svelte/motion';
    import { cubicOut } from 'svelte/easing';

    let inputNodes = [1, 1, 0, 1];
    let outputNodes = [1, 1, 0];

    let clientWidth;

    let animationStarted = false;

    function animateInitialLayout() {
        // Define initial positions of input and output nodes
        const inputNodePositions = [
            { x: (clientWidth - 200) / 2, y: 50 },
            { x: (clientWidth - 200) / 2, y: 100 },
            { x: (clientWidth - 200) / 2, y: 150 },
            { x: (clientWidth - 200) / 2, y: 200 }
        ];
        const outputNodePositions = [
            { x: (clientWidth + 160) / 2, y: 100 },
            { x: (clientWidth + 160) / 2, y: 150 },
            { x: (clientWidth + 160) / 2, y: 200 }
        ];

        // Animate input nodes
        inputNodes.forEach((node, index) => {
            anime({
                targets: `.input-node-${index}`,
                translateX: inputNodePositions[index].x,
                translateY: inputNodePositions[index].y,
                easing: 'easeInOutQuad',
                duration: 1000
            });
        });

        // Animate output nodes
        outputNodes.forEach((node, index) => {
            anime({
                targets: `.output-node-${index}`,
                translateX: outputNodePositions[index].x,
                translateY: outputNodePositions[index].y,
                easing: 'easeInOutQuad',
                duration: 1000
            });
        });
    }

    const startAnimation = () => {
        animationStarted = true;
        animateInitialLayout();
    };
</script>

<style>
    /* CSS styles for nodes */
    .node {
        position: absolute;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        border: 2px solid #3f3f3f;
        background-color: #3f3f3f;
        text-align: center;
        line-height: 40px;
        color: white;
    }
</style>

{#if !animationStarted}
    <div class="flex flex-row justify-center">
        <button class="btn variant-filled-secondary" on:click={startAnimation}>Start Animation</button>
    </div>
{:else}
<div bind:clientWidth={clientWidth} class="h-[400px] relative" in:ease>
    <!-- Input nodes -->
    {#each inputNodes as node, index}
        <div class="node input-node-{index}" style="left: {(clientWidth - 200) / 2}px; top: {index * 50 + 50}px;">{node}</div>
    {/each}
    <span class="absolute left-2 top-2">Input</span>

    <!-- Output nodes -->
    {#each outputNodes as node, index}
        <div class="node output-node-{index}" style="left: {(clientWidth + 160) / 2}px; top: {index * 50 + 100}px;">{node}</div>
    {/each}
    <span class="absolute right-2 top-2">Output</span>
</div>
{/if}