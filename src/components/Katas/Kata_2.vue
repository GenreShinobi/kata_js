<template>
    <div id="kata">
        <h1>Challenge #{{challengeID}}: {{title}}</h1> <h2>{{completionDate}}</h2>
        <div id="description">{{description}}</div>
        <div id="challenge">
            <div v-if="numList.length > 0"><strong>The NumList:</strong> {{numList}}</div>
            <div v-if="numList.length === 0"><strong>The NumList:</strong> [ No Numbers In List ]</div>
            Add to Num List:
            <input id="add" v-model="toAdd"/> <button v-on:click="addToNumList()">Add</button>
            <div><strong>Using Division:</strong> {{useDivision()}}</div>
            <div><strong>Without Division:</strong> {{noDivision()}}</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Kata_1",
        data () {
            return {
                challengeID: 2,
                title: 'Of Products',
                completionDate: 'Sept. 29, 2019',
                description: 'Given an array of integers, return a new array such that each element at index i of the new array is the product of all the numbers in the original array except the one at i.',
                numList: [],
                useDivList: [],
                noDivList: [],
                toAdd: 0
            }
        },
        methods: {
            useDivision: function () {
                let result = 1;
                if (this.numList.length !== this.noDivList.length) {
                    this.noDivList = [];
                    for (let i = 0; i < this.numList.length; i++){
                        result = result * this.numList[i];
                    }
                    for (let i = 0; i < this.numList.length; i++){
                        if (this.numList[i] !== 0) {
                            this.noDivList.push(result / this.numList[i]);
                        }
                    }
                }
                return this.noDivList;
            },
            noDivision: function () {
                if (this.numList.length !== this.noDivList.length) {
                    this.noDivList = [];
                    for (let i1 = 0; i1 < this.numList.length; i1++) {
                        let result = 1;
                        for (let i2 = 0; i2 < this.numList.length; i2++) {
                            if (i1 !== i2) {
                                result = result * this.numList[i2];
                            }
                        }
                        this.noDivList.push(result);
                    }
                }
                return this.noDivList;
            },
            addToNumList: function () {
                this.numList.push(parseInt(this.toAdd));
            }
        },
        computed: {
        }
    }
</script>

<style scoped>
    input[type=number]::-webkit-inner-spin-button,
    input[type=number]::-webkit-outer-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }
    input::placeholder {
        color: white;
    }
    input {
        background: none;
        border: 1px white dashed;
        padding: 5px;
        color: white;
    }

    button {
        background: none;
        color: white;
        border: 1px white dashed;
        height: 27px;
        cursor: pointer;
    }
    h1 {
        display: inline-block;
        text-align: left;
        font-size: 14px;
        margin-right: 15px;
    }
    h2 {
        width: 48%;
        display: inline-block;
        font-size: 12px;
        font-weight: normal;
    }
    div {
        margin-top: 5px;
        margin-bottom: 5px
    }
    #add {
        margin-right: 10px;
        width: 50px;
    }
    #challenge {
        padding: 25px;
    }
    #description {
        text-align: left;
        font-size: 14px;
        padding: 25px;
    }
    #k {
        width: 50px;
        text-align: center;
        margin-left: 5px;
    }
    #k:focus {
        outline: none;
    }
</style>