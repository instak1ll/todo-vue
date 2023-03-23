<script>
export default {
    props: ['title'],
    emits: ['remove']
}
</script>

<template>
    <li class="list-group-item d-flex justify-content-between align-items-center">
        {{ title }}
        <button class="btn btn-danger" @click="$emit('remove')">Eliminar</button>
    </li>
</template>