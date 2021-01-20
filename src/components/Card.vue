<template>
    <article :class="{ 'alt-style' : alternate }">
        <p>Prénom: {{ firstname }}</p>
        <p>Nom: {{ lastname }}</p>
        <p>Age: {{ age }}</p>
    </article>
</template>

<script>
export default {
    props: {
        firstname: {
            type: String,
            required: true,
        },
        lastname: {
            type: String,
            default: "valeur par defaut",
        },
        age: {
            type: Number,
            validator: (v) => v > 0,
        },
        alternate: {
            type: Boolean
        }
    }
}
</script>

<style>
.alt-style {
    color: red;
}
</style>