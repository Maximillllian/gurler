<template>
    <header>
        <div class="left">Gurler Ltd.</div>
        <div class="right">
            <LanguageSwitch @change-language="changeLanguage" />
        </div>
    </header>
</template>

<script>
import LanguageSwitch from './LanguageSwitch.vue';

export default {
    components: { LanguageSwitch },
    methods: {
        changeLanguage(language) {
            this.$emit('change-language', language);
        },
    },
};
</script>

<style scoped>
header {
    padding: 16px 40px;
    display: flex;
    justify-content: space-between;
    border-bottom: 1px solid lightgrey;
}

@media screen and (max-width: 600px) {
    header {
        padding: 16px 20px;
    }
}
</style>
