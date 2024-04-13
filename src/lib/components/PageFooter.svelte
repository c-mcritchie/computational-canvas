<script>
    let balls = [];
    for (let i = 6; i > 1; i--) {
        balls.push({
            size: (10 * i)
        });
    }
    for (let i = 1; i < 7; i++) {
        balls.push({
            size: (10 * i),
        });
    }
</script>

<hr class="!border-t-2 bg-neutral-100 flex justify-center content-center mt-12">
<div class="container p-8 flex justify-center content-center mx-auto">
    <div class="container lg:flex gap-4 justify-center">
        <div class="flex gap-4 justify-center content-center ">
            {#each balls as ball (ball)}
                {#key ball}
                <div class="flex-col flex mx-auto">
                    <div class="my-auto rounded-full justify-center content-center bg-black"
                         style="width: {ball.size}px; height: {ball.size}px;"></div>
                </div>
                {/key}
            {/each}
        </div>
    </div>
</div>
