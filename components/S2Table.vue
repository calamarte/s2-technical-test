<template>
    <table class="w-full border-collapse border border-slate-500">
        <thead class="sticky bg-gray-500 top-0">
            <tr>
                <th
                    v-for="header in computedHeaders"
                    :key="header.key"
                    class="border border-slate-600"
                    v-text="header.label"
                />
            </tr>
        </thead>
        <tbody>
            <tr v-for="(row, index) in dataSource" :key="index">
                <td 
                    v-for="header in computedHeaders"
                    :key="`${index}-${header.key}`"
                    class="border text-center border-slate-600"
                    v-text="row[header.key]"
                />
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
    props: {
        headers: {
          type: Array,
          default: () => []  
        },
        dataSource: {
            type: Array,
            default: () => []
        }
    },
    data: () => ({
        
    }),
    computed: {
        computedHeaders() {
            return this.headers.map(h => {

                if (typeof h === 'object') {
                    return h;
                }

                return { label: h, key: h }
            })
        }
    }
}
</script>