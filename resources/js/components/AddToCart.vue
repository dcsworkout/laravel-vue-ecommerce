<template>
    <div>
        <hr />
        <button
            class="btn btn-warning text-center"
            v-on:click.prevent="addProductToCart()"
        >
            Añadir al Carrito
        </button>
    </div>
</template>

<script>
export default {
    data() {},
    props: ["productId", "userId"],
    methods: {
        addProductToCart() {
            if (this.userId == 0) {
                this.$toastr.e(
                    "Debes iniciar sesión para añadir productos al Carrito"
                );
                return;
            }
        },
    },
    mounted() {
        console.log("Component mounted.");
    },
};
</script>
