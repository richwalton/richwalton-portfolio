<template>
    <header class="header" :class="{sticky: $route.path === '/' || $route.path.includes('/projects/')}">
     <meta name="viewport" content="width=device-width, initial-scale=1">
        <div class="container">
            <div class="left">
                <g-link :to="{ name: 'home' }" class="home-link">
                    <img 
                        src="../../static/rich-walton-dev-logo-sml.png"
                        :alt="settings.site_name" 
                        class="logo"
                    />
                </g-link>
            </div>
            <nav class="nav right">
                <g-link class="nav__link" to="/journal">Journal</g-link>
                <g-link class="nav__link" to="/contact">Say Hi!</g-link>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
  data() {
    return {
        logo: require("../../static/rich-walton-dev-logo-sml.png"),
        settings: require("../../data/theme.json")
    }
  }
}
</script>

<style scoped>
.header {
    position: relative;
    height: 4.5rem;
    z-index: 10;
}
.header.sticky {
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(255,255,255,0.96);
    width: 100%;
}
.header > .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 100%;
}
.home-link {
    text-decoration: none;
}
.logo {
    height: 1.7rem;
}
.site-name {
    font-size: 0.9rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-decoration: none;
    text-transform: uppercase;   
}
.nav > * {
    font-size: 0.9rem;
    font-weight: 600;
    text-decoration: none;
    margin-top: 4px;
    margin-right: 3rem;
    padding-bottom: 4px;
    border-bottom: 1px solid;
    border-color: transparent;
    transition: border 0.15s;
}
.nav > *:last-of-type {
    margin: 0;
}
.nav > *:hover {
    border-color: inherit;
}
.nav > .active {
    border-color: inherit;
}
@media (max-width: 979px) {
    .header > .container {
    display: flex;
    flex-direction: column;
    align-items: center;  
    }
    .logo {
    height: 1.5rem;
    margin:10px 0;
    min-width:200px;
}
} 
</style>
