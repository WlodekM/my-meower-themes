<script>
    import { params } from "@roxi/routify"
    import { themes } from "../../../lib/themes.js"
    import ThemePreview from "../../../components/ThemePreview.svelte";
</script>

{#if themes[$params.theme]}
    {@const theme = themes[$params.theme]}
    <center>
        <h1>
            /themes/{$params.theme}
            <br>
            <a href="/">back</a>
        </h1>
        <ThemePreview size={0.75} theme={themes[$params.theme].json}/>
    </center>
    <h2>Info:</h2>
    <ul>
        <li>Name: {theme.title}</li>
        <li>Author: {theme.author}</li>
        <li>Description: {themes.description}</li>
    </ul>
    <textarea style="width: calc(100vw - 8px * 6)" rows="1">{JSON.stringify(themes[$params.theme].json)}</textarea>
{:else}
    Not found
{/if}