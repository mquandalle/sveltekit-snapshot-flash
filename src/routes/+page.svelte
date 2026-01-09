<script lang="ts">
    import type { Snapshot } from "./$types";

    let comment = $state("hello");

    export const snapshot: Snapshot<string> = {
        capture: () => comment,
        restore: (value) => (comment = value),
    };

    $inspect(comment);
</script>

<form method="POST">
    <label for="comment">Edit this field</label><br />
    <textarea id="comment" bind:value={comment} />
</form>

<p>Then go to <a href="/another-page">another page</a> and come back.</p>
<p>
    Open the console. When we navigate back, there is a flash with the default
    value ("hello") before the value is restored.
</p>
