<template>
    <div class="content">
        <the-header @change-language="changeLanguage" />
        <div class="sorry-message">
            <site-not-working :language="language" />
        </div>
    </div>
</template>

<script>
import SiteNotWorking from './components/SiteNotWorking.vue';
import TheHeader from './components/TheHeader.vue';
import { DEFAULT_LANGUAGE } from './utils/constants';

export default {
    name: 'App',
    data() {
        return {
            language: DEFAULT_LANGUAGE,
        };
    },
    components: {
        TheHeader,
        SiteNotWorking,
    },
    methods: {
        changeLanguage(language) {
            this.language = language;
        }
    },
};
</script>

<style>
:root {
    --main-color: #2c3e50;
    --blue: #6246ea;
    --light-blue: #a2a2ed;

    --hover-color: var(--light-blue);
    --active-color: var(--blue);
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: var(--main-color);
}

.content {
    height: 100vh;
    display: flex;
    flex-direction: column;
}

.sorry-message {
    display: flex;
    place-content: center;
    align-items: center;
    height: 100%;
    padding: 20px;
}
</style>
