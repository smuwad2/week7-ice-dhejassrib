<script>
    export default { 
        // Add Code Here to complete the task
        // Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!
        data() {
            return {
                x: 0,
                selectedOp: '',
                y: 0,
                operators: ['+', '-', '*', '/', '%']
            }
        },
        computed: {
            result() {
                // const { x, y, selectedOp } = this;
                // if (selectedOp === '+') return x + y;
                // if (selectedOp === '-') return x - y;
                // if (selectedOp === '*') return x * y;
                // if (selectedOp === '/') {
                //     if (y !== 0) {
                //         return x/y
                //     }
                //     else {
                //         return  "Error"
                //     }
                // };
                // if (selectedOp === '%') return x % y;
                
                // return y !== 0 ? x / y : 'Error: ÷0';
                // return '';

                switch(this.selectedOp) {
                    case "+": return this.x + this.y;
                    case "-": return this.x - this.y;
                    case "*": return this.x * this.y;
                    case "/": return this.x / this.y;
                    case "%": return this.x % this.y;
                }
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
