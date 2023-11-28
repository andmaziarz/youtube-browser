<template>
    <div>
        <input v-model="inputSearch"/>
        <button @click="onSearch">Search</button>
    </div>    
</template>

<script>
export default {
    name: 'SearchBar',
    data() {
        return {
            inputSearch: ''
        }
    },
    methods: {
        onSearch(){
            this.$emit('termChange', this.inputSearch)
        }
    }
};
</script>

<style scoped>
    input {
        width: 50%;
    }
    div {
        text-align: center;
        margin: 20px;
    }
</style>