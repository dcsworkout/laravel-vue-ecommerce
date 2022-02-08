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
    data() {
        return {};
    },
    props: ["productId", "userId"],
    methods: {
        //Verifica si el usuario ha inciado sesión.
        async addProductToCart() {
            if (this.userId == 0) {
                this.$toastr.e(
                    "Debes iniciar sesión para añadir productos al Carrito"
                );
                return;
            }

            //Si ha inciado sesión añade al carrito
            let response = await axios.post("/cart", {
                product_id: this.productId,
            });

            this.$root.$emit("changeInCart", response.data.items);
        },
    },
    mounted() {},
};
</script>
