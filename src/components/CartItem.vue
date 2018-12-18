<template>
    <div class="list-group-item">
        <div class="row">
            <div class="col-md-8">{{name}}</div>
            <div class="col-md-2">${{priceInCents/100}}</div>
            <div class="col-md-2">{{quantity}}</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CartItem',
    props: ['name', 'priceInCents', 'quantity'],
}
</script>

