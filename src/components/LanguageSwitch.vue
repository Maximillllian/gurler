<template>
    <div>
        <span
            class="item"
            :class="{ active: isEnglish }"
            @click="setEnglish"
            >EN</span
        >
        /
        <span
            class="item"
            :class="{ active: !isEnglish }"
            @click="setTurkish"
            >TR</span
        >
    </div>
</template>

<script>
import { DEFAULT_LANGUAGE, LANGUAGES } from '@/utils/constants';
export default {
    data() {
        return {
            language: DEFAULT_LANGUAGE,
        };
    },
    watch: {
        language(value) {
            this.$emit('change-language', value);
        },
    },
    computed: {
        isEnglish() {
            return this.language === LANGUAGES.ENGLISH;
        },
    },
    methods: {
        setLanguage(language) {
            this.language = language;
        },
        setEnglish() {
            this.setLanguage(LANGUAGES.ENGLISH);
        },
        setTurkish() {
            this.setLanguage(LANGUAGES.TURKISH);
        },
    },
};
</script>

<style scoped>
.item {
    cursor: pointer;
    transition: all .15s ease-in-out;
}

.item:hover {
    color: var(--active-color);
}

.active {
    color: var(--active-color);
}
</style>
