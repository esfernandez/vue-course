<script setup>
    import {computed, reactive, onMounted, useSlots} from 'vue';

    

    const slots = useSlots()

    onMounted(() => {
        console.log(slots.default())
    })

</script>

<style>

</style>