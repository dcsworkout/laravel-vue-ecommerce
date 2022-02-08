<template>
    <div>
        <li class="nav-item">
            <a href="/checkout" class="btn btn-warning btn-sm">
                Carrito
                <div style="display: inline; color: #dc143c">
                    {{ itemCount }}
                </div>
            </a>
        </li>
    </div>
</template>

<script>
export default {
    data() {
        return {
            itemCount: "",
        };
    },
    methods: {
        async getItemsCartOnPageLoad() {
            let response = await axios.post("/cart");
            this.itemCount = response.data.items;
        },
    },
    mounted() {
        this.$root.$on("changeInCart", (item) => {
            this.itemCount = item;
        });
    },
    created() {
        this.getItemsCartOnPageLoad();
    },
};
</script>
