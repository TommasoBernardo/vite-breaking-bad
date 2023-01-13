
<template>
    <section>
        <div class="container">
            <div class="row">
                <div class="col-3 offset-4">
                    <select class="form-select-sm" v-model="Input" v-on:change="$emit('search', Input)">
                        <option selected value="Alien">Alien</option>
                        <option value="Laval">Laval</option>
                        <option value="Vylon">Vylon</option>
                        <option value="Inzektor">Inzektor</option>
                        <option value="Umi">Umi</option>
                        <option value="Gusto">Gusto</option>
                    </select>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    name: 'SelectComponents',
    data() {
        return {
            Input: ''
        }
    },
}
</script>