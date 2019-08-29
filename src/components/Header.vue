<template>
    <header>
        <input v-model="inputData" type="text" name="todoInput" id="todoInput" placeholder="What's the plan batman?" >
        <button @click="createTodo" class="submit" id="createTodo" >+</button>
    </header>
</template>

<script>
export default {
    data: function() {
        return {
            inputData: ''
        }
    },
    methods: {
        createTodo() {
            this.$emit('createTodo', this.inputData);

            this.inputData = '';
        }
    }
}
</script>

<style lang="scss" scoped>
    header {
        display: flex;

        input {
            flex: 1;
            height: 50px;
            box-sizing: border-box;
            font-size: 20px;
            text-indent: 15px;
        }

        .submit {
            width: 50px;
            height: 50px;
            font-size: 28px;
            cursor: pointer;
            color: #000;
            background: wheat;
            border: none;
            outline: none;
            font-weight: 500;

            &:hover {
                background: #ccb894;
            }

            &:active {
                background: #a28f6c;
            }
        }
    }
</style>