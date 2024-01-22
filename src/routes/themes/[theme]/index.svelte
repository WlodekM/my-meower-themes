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
    <textarea style="width: calc(100vw - 8px * 3)" rows="10">{JSON.stringify(themes[$params.theme].json)}</textarea>
{:else}
    Not found
{/if}