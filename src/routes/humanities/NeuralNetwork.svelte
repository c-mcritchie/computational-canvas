<script>
    import { onMount } from 'svelte';
    import anime from 'animejs';
    import { tweened } from 'svelte/motion';
    import { cubicOut } from 'svelte/easing';
    import { fade } from 'svelte/transition';

    let inputNodes = [1, 1, 0, 1];
    let outputNodes = [0, 0, 1];
    let hidden1Nodes = ["", "", "", "", ""];
    let hidden2Nodes = ["", "", "", "", ""];
    let hidden3Nodes = ["", "", "", ""];
    let clientWidth;

    let animationStarted = false;
    let button = true;
    let IOlabels = true;
    let label;
    let hiddenLabel = 0;

    function wait(ms) {
        return new Promise((resolve) => {
            setTimeout(resolve, ms);
        });
    }

    const size = tweened(60, {
        duration: 800,
        easing: cubicOut
    });

    async function animateGlow() {
        // Animate node text appearing
        anime({
            targets: '.text-i',
            opacity: '100%',
            easing: 'easeInOutQuad',
            duration: 1000,
            complete: async () => {
                await wait(300);
                anime({
                    targets: '.text-i',
                    opacity: '0%',
                    easing: 'easeInOutQuad',
                    duration: 1000
                });
            }
        });
        // Animate gray to lighter gray glow effect for input nodes
        // then turn off glow effect
        const layers = ['.input-node', '.hidden-node-1', '.hidden-node-2', '.hidden-node-3', '.output-node'];
        for (let layer of layers) {
            anime({
                targets: layer,
                backgroundColor: '#8a8a8a',
                easing: 'easeInOutQuad',
                duration: 1000,
                complete: () => {
                    anime({
                        targets: layer,
                        backgroundColor: '#3f3f3f',
                        easing: 'easeInOutQuad',
                        duration: 1000
                    });
                }
            });
            if (layer === '.output-node') continue;
            await wait (1200);
        }
        // Animate node text appearing
        anime({
            targets: '.text-o',
            opacity: '100%',
            easing: 'easeInOutQuad',
            duration: 1000,
        });
    }



    function animateInitialLayout() {
        // Animate input nodes
        anime({
            targets: `.input-node`,
            left: `${(clientWidth - 300) / 2}px`,
            easing: 'easeInOutQuad',
            duration: 1000
        });


        // Animate output nodes

        anime({
            targets: `.output-node`,
            left: `${(clientWidth + 300) / 2}px`,
            easing: 'easeInOutQuad',
            duration: 1000
        });

    }

    const startAnimation = () => {
        button = false;
        size.set(400).then(async () => {
            animationStarted = true;
            await wait(3000);
            IOlabels = false;
            await wait(500)
            animateInitialLayout();
            await wait(1000);

            anime({
                targets: '.hidden-layers',
                opacity: '100%',
                easing: 'easeInOutQuad',
                duration: 1000
            })
            await wait(1000);
            hiddenLabel = 1;
            await wait(1000);
            hiddenLabel = 2;
            await wait(100);
            animateGlow();

        });
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
    .text-o {
        opacity: 0%;
    }

    .text-i {
        opacity: 0%;
    }


    .hidden-layers {
        opacity: 0%;
    }

    .line {
        stroke: #3f3f3f;
        stroke-width: 2px;
    }
</style>

<div class="card p-2 my-6 " style="height: {$size}px">
    {#if button}
        <div class="flex flex-row justify-center">
            <button class="btn variant-filled-secondary" on:click={startAnimation} out:fade>Start Animation</button>
        </div>
    {/if}
    {#if animationStarted}
        <div bind:clientWidth={clientWidth} class="h-full relative" in:fade>
            <!-- Input nodes -->
            {#each inputNodes as node, index}
                <div class="node input-node" style="left: {(clientWidth - 100) / 2}px; top: {index * 50 + 100}px;"><span class="text-i">{node}</span></div>
            {/each}
            {#if IOlabels}
                <span style="left: {(clientWidth - 100) / 2}px; top: 70px;" out:fade class="absolute">Input</span>
            {/if}

            {#each hidden1Nodes as node, index}
                <div class="node hidden-layers hidden-node-1" in:fade style="left: {(clientWidth) / 2 - 75}px; top: {index * 50 + 75}px;"> </div>
            {/each}
            {#each hidden2Nodes as node, index}
                <div class="node hidden-layers hidden-node-2" in:fade style="left: {(clientWidth) / 2}px; top: {index * 50 + 75}px;"> </div>
            {/each}
            {#each hidden3Nodes as node, index}
                <div class="node hidden-layers hidden-node-3" in:fade style="left: {(clientWidth) / 2 + 75}px; top: {index * 50 + 100}px;"> </div>
            {/each}

            {#if hiddenLabel === 1}
                <span style="left: {(clientWidth) / 2 - 50}px; top: 40px;" in:fade out:fade class="absolute">Hidden Nodes</span>
            {/if}

            {#if hiddenLabel === 2}
                <span style="left: {(clientWidth) / 2 - 150}px; top: 40px;" in:fade out:fade class="absolute">All nodes in adjacent layers are connected</span>
            {/if}

            <!-- Output nodes -->
            {#each outputNodes as node, index}
                <div class="node output-node" style="left: {(clientWidth + 100) / 2}px; top: {index * 50 + 120}px;"><span class="text-o">{node}</span></div>
            {/each}
            {#if IOlabels}
                <span style="left: {(clientWidth + 75) / 2}px; top: 70px;" out:fade class="absolute">Output</span>
            {/if}
        </div>
    {/if}
</div>
