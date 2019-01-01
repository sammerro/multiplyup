<template>
    <div class="result-container">
        <h2 :class="headingClass"> {{ text }} </h2>
        <button class="btn" @click="onNextButton">
            Next
        </button>
    </div>
</template>

<script>

export default {
    props: {
        ifGoodAnswer: Boolean
    },
    computed: {
        text() {
            if (this.ifGoodAnswer) return `Great answer!`;
            return `Bad answer`;
        },
        headingClass() {
            if (this.ifGoodAnswer) return `good`;    
            return `bad`;        
        }
    },
    methods: {
        onNextButton () {
            this.$emit('nexted');
        }
    }
}
</script>

<style lang="scss" scoped>


.result-container {
    width: 100%;
    height: 100%;
    background-color: var(--bg-color-second);
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    align-items: center;
}

.good {
    color: var(--success-text-color);
}

.bad {
    color: var(--error-text-color); 
}

</style>