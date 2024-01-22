<script>
    import { params } from "@roxi/routify"
    import { themes } from "../../../lib/themes.js"
    import ThemePreview from "../../../components/ThemePreview.svelte";
</script>

{#if themes[$params.theme]}
    <center>
        <h1>
            {themes[$params.theme].title}
        </h1>
        <ThemePreview size={1} theme={themes[$params.theme].json}/>
    </center>
{:else}
    Not found
{/if}