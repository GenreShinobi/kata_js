<template>
    <div>
        <Kata_1/>
    </div>
    
</template>

<script>
    import Kata_1 from "@/components/Katas/Kata_1";
    export default {
        name: "Katas",
        components: {
            Kata_1
        }
    }
</script>

<style scoped>

    #kata {
        border: 1px white dashed;
        padding: 5px;
        padding-bottom: 15px;
    }
</style>