<template>
    <div class="container">
        <form v-on:submit.prevent="addItemToCart">
            <div class="row">
                <label>
                    <h6>Quantity</h6>
                    <input type="text" name="quantity" v-model="form.quantity" />
                </label>
            </div>
            <div class="row">
                <label>
                    <h6>Product</h6>
                    <select v-model="form.productId">
                        <option
                            v-for="(product, index) in products"
                            v-bind:key="index"
                            v-bind:value="product.id"
                            >{{product.name}}</option>
                    </select>
                </label>
            </div>
            <div>
                <button>Submit</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'AddItem',
    props: ['products', 'addToCart'],
    data: function() {
        return {
            form: {
                quantity: 0,
                productId: 40
            }
        }
    },

    methods:{
        addItemToCart(){
            this.addToCart(this.form);
        }
    }
}
</script>

