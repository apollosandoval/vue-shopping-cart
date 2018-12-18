<template>
    <div class="container">
        <h1>Items</h1>
        <div class="list-group">
            <div class="list-group-item">
                <div class="row">
                    <div class="col-md-8">Total</div>
                    <div class="col-md-2">${{ total }}</div>
                </div>
            </div>
        </div>
        <div class="list-group">
            <div class="list-group-item">
                <div class="row">
                    <div class="col-md-8">Product</div>
                    <div class="col-md-2">Price</div>
                    <div class="col-md-2">Quantity</div>
                </div>
            </div>
        </div>
        <!-- Cart Items will go here -->
        <CartItem
            v-for="(item, index) in items"
            v-bind:name="item.product.name"
            v-bind:priceInCents="item.product.priceInCents"
            v-bind:quantity="item.quantity"
            v-bind:key="index" />
    </div>
</template>

<script>
import CartItem from './CartItem.vue'

export default {
    name: 'CartItemList',
    components: {
        CartItem
    },
    props: ['items'],
    computed: {
        total: function() {
            return this.items.reduce( (acc, item) => {return acc+item.product.priceInCents*item.quantity/100}, 0)
        }
    }
}
</script>
