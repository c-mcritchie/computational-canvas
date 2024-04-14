<script lang="ts">
    let elemCarousel : HTMLDivElement;
    export let imgNames;
    export let beforeAlt;
    export let afterAlt;
    export let afterPath;
    export let title;


    function carouselLeft(): void {
        const x =
            elemCarousel.scrollLeft === 0
                ? elemCarousel.clientWidth * elemCarousel.childElementCount // loop
                : elemCarousel.scrollLeft - elemCarousel.clientWidth; // step left
        elemCarousel.scroll(x, 0);
    }



    function carouselRight(): void {
        const x =
            elemCarousel.scrollLeft === elemCarousel.scrollWidth - elemCarousel.clientWidth
                ? 0 // loop
                : elemCarousel.scrollLeft + elemCarousel.clientWidth; // step right
        elemCarousel.scroll(x, 0);
    }
</script>

<main class="card p-4 grid grid-cols-[auto_1fr_auto] gap-4 items-center">
    <!-- Button: Left -->
    <button type="button" class="btn-icon variant-filled" on:click={carouselLeft}>
        <i class="font-bold text-lg">&lt;</i>
    </button>
    <!-- Full Images -->
    <div bind:this={elemCarousel} class="snap-x snap-mandatory scroll-smooth flex overflow-x-auto">
        {#each imgNames as imgName}
            <img
                    class="snap-center w-[1024px] rounded-container-token"
                    src="/{imgName}{afterPath}"
                    alt="{beforeAlt} {imgName.toLowerCase()} {afterAlt}"
                    loading="lazy"
            />
        {/each}
    </div>
    <!-- Button: Right -->
    <button type="button" class="btn-icon variant-filled" on:click={carouselRight}>
        <i class="font-bold text-lg">&gt;</i>
    </button>
</main>