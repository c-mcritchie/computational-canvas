<script lang="ts">
    export let citation;
    if (typeof citation === "number") {
        citation = [citation];
    }
</script>

<span>
{#each citation as c, i}
    [<a href="/sources/#{c}">{c}</a>]{#if i < citation.length - 1}, {/if}
{/each}
</span>
