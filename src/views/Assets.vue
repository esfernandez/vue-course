<template>
    <div>
        <AlpGrid>
            <AlpGridColumn name="Name" field="name" />
            <AlpGridColumn name="Last name" field="lastname" />
            <AlpGridColumn name="Age" field="age" />
        </AlpGrid>

    </div>
</template>

<script setup>
    import AlpGrid from '../components/AlpGrid.vue';
</script>