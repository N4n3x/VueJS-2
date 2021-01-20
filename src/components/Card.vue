<template>
    <article :class="{ 'alt-style' : alternate }">
        <p>Prénom: {{ firstname | capitalize }}</p>
        <p>Nom: {{ lastname | capitalize }}</p>
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
    },
    filters: {
        capitalize(value){
            return value.charAt(0).toUpperCase() + value.slice(1);
        }
    }
}
</script>

<style>
.alt-style {
    color: red;
}
</style>