<template>
    <nav class="navbar navbar-dark bg-dark">
        <a class="navbar-brand">&copy; {{copyright}}</a>
    </nav>
</template>

<script>
export default {
    name: 'CartFooter',
    data: () => ({
        copyright: '2018'
    })
}
</script>
