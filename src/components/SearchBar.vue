<template>
    <div class="input-group w-50 ml-auto p-2">
        <input v-model="inputSearch" class="form-control rounded " placeholder="Search" />
        <button @click="onSearch" class="btn btn-outline-secondary"><i class="bi bi-search"></i></button>
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
            this.$emit('termSearch', this.inputSearch)
        }
    }
};
</script>
<style scoped>
    div{
        margin: 20px 0 20px 0;
    }
</style>