<template>
    <div>
        <kata_2/>
        <Kata_1/>
    </div>
    
</template>

<script>
    import Kata_1 from "@/components/Katas/Kata_1";
    import Kata_2 from "@/components/Katas/Kata_2";

    export default {
        name: "Katas",
        components: {
            Kata_1,
            Kata_2
        }
    }
</script>

<style scoped>

    #kata {
        border: 1px white dashed;
        padding: 15px;
        text-align: left;
        font-size: 14px;
        margin: 10px;
    }
</style>