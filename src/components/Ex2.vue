<script>
export default { 
    // Add code in appropriate places
    data() {
        return {
            items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
            newItem: ''
        }
    },
    methods: {
        addItem() {
            // push new item into items array
            this.items.push(this.newItem.trim());
            // this.newItem = ''; // clear input
        }
        // deleteItem(index) {
        //     this.items.splice(index, 1);
        // }
    }
}
</script>

<template>
    <h2>Shopping Cart</h2>

    <ul>
        <li v-for="(item, idx) in items">
            {{ item }}
            <!-- <button @click=deleteItem(idx)>Delete!</button> -->
            <button @click="items.splice(idx)">Delete!</button>
        </li>
    </ul>

    <input type="text" v-model="newItem"></input>
    <button @click="addItem">Add!</button>
</template>
