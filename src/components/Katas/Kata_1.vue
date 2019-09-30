<template>
    <div id="kata">
        <h1>{{headerL}}</h1> <h2>{{headerR}}</h2>
        <div id="description">{{description}}</div>
        <div id="challenge">
            <div v-if="numList.length === 0"> <strong>NumList:</strong> [ No Numbers In List ]</div>
            <div v-if="numList.length > 0"> NumList: {{numList}}</div>
            <br>
            Add to Num List:
            <input id="add" v-model="toAdd">
            <button v-on:click="function () {addNumToList(); findAddends();}">Add</button>
            <br>
            <strong>k:</strong> <input id="k" v-model="k" type="number" v-on:input="findAddends()">
            <br>
            Does the List of Numbers contain addends of {{k}}?
            <br>
            <div v-if="hasAddends">
                Yes! {{addendOne}} and {{addendTwo}} are both addends of {{k}}.
            </div>
            <div v-if="!hasAddends">
                No. The list does not contain addends of {{k}}.
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Kata_1",
        data () {
            return {
                headerL: 'Challenge #1: Of Addends',
                headerR: 'Sept. 28, 2019',
                description: 'Given a list of numbers, and a number k, return whether any 2 numbers are addends of k.',
                numList: [],
                k: 17,
                addendOne: '',
                addendTwo: '',
                toAdd: 0
            }
        },
        methods: {
            findAddends: function () {
                let found = false;
                this.addendOne = '';
                this.addendTwo = '';
                for (let i1 = 0; i1 < this.numList.length; i1++){
                    for (let i2 = 0; i2 < this.numList.length; i2++) {
                        if (i1 !== i2 && this.numList[i1] + this.numList[i2] === parseInt(this.k)){
                            this.addendOne = this.numList[i1];
                            this.addendTwo = this.numList[i2];
                            found = true;
                        }
                    }
                }
                return found;
            },
            addNumToList: function () {
                if (this.toAdd !== "") {
                    this.numList.push(parseInt(this.toAdd, 10));
                }
            }
        },
        computed: {
            hasAddends: function () {
                if (this.addendOne !== ''){
                    return true;
                }
                return false
            }
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