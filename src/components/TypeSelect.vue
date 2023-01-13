
<template>
    <section>
        <div class="container">
            <div class="row">
                <div class="col-3 offset-4">
                    <select class="form-select-sm" v-model="userInput" v-on:change="$emit('search', userInput)">
                        <option selected value="Alien">Alien</option>
                        <option value="Laval">Laval</option>
                        <option value="Vylon">Vylon</option>
                        <option value="Inzektor">Inzektor</option>
                    </select>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    name: 'Search',
    data() {
        return {
            userInput: ''
        }
    },
}
</script>