<script>
    import {page} from '$app/stores';
</script>

<h3>Oops, something hasn't worked properly, use the error code and contact me with your problem.</h3>
<h3>{$page.status}: {$page.error.message}</h3>
