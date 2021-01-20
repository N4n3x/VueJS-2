<template>
    <div>
        <p>Valeur actuel: {{ count }}</p>
        <p>Valeur doublé: {{ double }}</p>
        <button @click="count += 1"> + </button> 
        <button @click="count -= 1"> - </button>

        <p>Valeur -1: {{ getSetCount }}</p>
        <button @click="getSetCount = 1"> set </button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            count: 0,
        }
    },
    computed: {
        double(){
            return this.count *2
        },
        getSetCount: {
            get(){
                return this.count -1
            },
            set(v){
                this.count = v + 1;
            }
        }
    },
    watch: {
        count(newVal, oldVal) {
            console.log(newVal, oldVal);
        }
    }
}
</script>