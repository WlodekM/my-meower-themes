<script context="module">
    import { Router, createRouter } from '@roxi/routify'
    import routes from '../.routify/routes.default.js'

    import "./style.css"

    export const router = createRouter({ routes })
</script>

<Router {router} />
