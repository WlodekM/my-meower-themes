<script>
    // import ExamplesSplash from '@/routes/examples/[mode]/__components/ExamplesSplash.svelte'
    //VS code cant find the themePreview component

    //@ts-ignore
    import ThemePreview from "../components/ThemePreview.svelte";
    import { themes } from "../lib/themes.js"
</script>

<!-- Remove this element to remove the Routify Welcome content. 
     It is also safe to remove the src/routes/examples folder. -->
<div class="grid">
    {#each Object.keys(themes) as themeID}
        <div class="theme">
            <ThemePreview size={0.5} theme={themes[themeID].json}/>
            {themes[themeID].title}
        </div>
    {/each}
</div>

<style>
    .grid {
        display: grid;
        gap: 5px;
        grid-template-columns: auto auto auto auto;
    }
</style>