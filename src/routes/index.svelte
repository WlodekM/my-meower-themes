<script>
    // import ExamplesSplash from '@/routes/examples/[mode]/__components/ExamplesSplash.svelte'
    //VS code cant find the themePreview component

    //@ts-ignore
    import ThemePreview from "../components/ThemePreview.svelte";
    import { themes } from "../lib/themes.js"
</script>

<!-- Remove this element to remove the Routify Welcome content. 
     It is also safe to remove the src/routes/examples folder. -->
<center>
    <h1>
        WlodekM's super cool themes
    </h1>
</center>
<div class="grid">
    {#each Object.keys(themes) as themeID}
        <a href="/themes/{themeID}">
            <div class="theme">
                <ThemePreview size={0.5} theme={themes[themeID].json}/>
                {themes[themeID].title}
            </div>
        </a>
    {/each}
</div>

<style>
    .grid {
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        gap: 5px;
    }
    .theme {
        flex: 1;
        min-width: calc(890px * 0.5);
        background: #333;
        padding: 10px;
        border-radius: 10px;
        color: #eee !important;
    }
    :global(.theme div svg) {
        border-radius: 5px;
    }
</style>