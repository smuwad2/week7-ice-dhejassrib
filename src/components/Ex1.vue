<script>
    export default { 
        // Add Code Here to complete the task
        // Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!
        data() {
            return {
                x: '',
                selectedOp: '',
                y: '',
                operators: ['+', '-', '*', '/']
            }
        },
        computed: {
        result() {
            const { x, y, selectedOp } = this;
            if (selectedOp === '+') return x + y;
            if (selectedOp === '-') return x - y;
            if (selectedOp === '*') return x * y;
            if (selectedOp === '/') return y !== 0 ? x / y : 'Error: ÷0';
            return '';
        }
    }
    }
</script>

<template>
    <p>x <input v-model.number="x"></p>
    <select v-model="selectedOp">
        <option v-for="op in operators" >{{ op }}</option>
    </select>
    <p>y <input v-model.number="y"></p>
    
    <p>---------------------</p>

    <p>= {{result}}</p>
</template>

<style scoped>
    p, input { font-family: monospace; }
    p { white-space: pre; }

</style>
