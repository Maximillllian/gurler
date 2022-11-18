<template>
    <div class="text">
        {{ sorryText }}
    </div>
</template>

<script>
import { DEFAULT_LANGUAGE } from '../utils/constants';

const SORRY = {
    english: 'Sorry, the site is not working for technical reasons. Come back later',
    turkish: 'Afedersiniz teknik konularda sait çalışmıyor da sonra sizinle',
};

export default {
    props: {
        language: {
            type: String,
            required: false,
            default: DEFAULT_LANGUAGE,
        },
    },
    computed: {
        sorryText() {
            return SORRY[this.language];
        },
    }
}
</script>

<style>
.text {
    font-size: 36px;
}

@media screen and (max-width: 600px) {
    .text {
        font-size: 24px;
    }
}
</style>