<template>
    <form @submit.prevent="submitForm">
        <button type="submit">Send</button>
        <button @click.prevent="$emit('custom-event', new Date())">event perso</button>
    </form>
</template>

<script>
export default {
    methods: {
        submitForm(){
            alert("Envoyé !")
        }
    }
}
</script>