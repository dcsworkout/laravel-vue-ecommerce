<template>
    <div>
        <div class="container" style="margin-top: 200px">
            <div class="row">
                <div class="col-lg-8 col-md-8 col-sm-7 col-xs-12">
                    <div class="box">
                        <h3 class="box-title">Select Your Hosting Plan</h3>
                        <div class="plan-selection">
                            <div class="plan-data">
                                <input
                                    id="question1"
                                    name="question"
                                    type="radio"
                                    class="with-font"
                                    value="sel"
                                />
                                <label for="question1">Personal</label>
                                <p class="plan-text">
                                    1 install | 25K visits/month | 10 GB local
                                    storage
                                </p>
                                <span class="plan-price">$29 / mo</span>
                            </div>
                        </div>
                        <div class="plan-selection">
                            <div class="plan-data">
                                <input
                                    id="question2"
                                    name="question"
                                    type="radio"
                                    class="with-font"
                                    value="sel"
                                />
                                <label for="question2">Profesional</label>
                                <p class="plan-text">
                                    Up to 10 installs | 100K visits/month | 20
                                    GB local storage
                                </p>
                                <span class="plan-price">$99 / mo</span>
                            </div>
                        </div>
                        <div class="plan-selection">
                            <div class="plan-data">
                                <input
                                    id="question3"
                                    name="question"
                                    type="radio"
                                    class="with-font"
                                    value="sel"
                                />
                                <label for="question3">Business</label>
                                <p class="plan-text">
                                    Up to 25 installs | 400K visits/month | 30
                                    GB local storage
                                </p>
                                <span class="plan-price">$249 / mo</span>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4 col-md-4 col-sm-5 col-xs-12">
                    <div class="widget">
                        <h4 class="widget-title">Order Summary</h4>
                        <div class="summary-block">
                            <div class="summary-content">
                                <div class="summary-head">
                                    <h5 class="summary-title">Personal</h5>
                                </div>
                                <div class="summary-price">
                                    <p class="summary-text">$29 / mo</p>
                                    <span class="summary-small-text pull-right"
                                        >1 month</span
                                    >
                                </div>
                            </div>
                        </div>
                        <div class="summary-block">
                            <div class="summary-content">
                                <div class="summary-head">
                                    <h5 class="summary-title">
                                        Website Security Essential
                                    </h5>
                                </div>
                                <div class="summary-price">
                                    <p class="summary-text">$229 / mo</p>
                                    <span class="summary-small-text pull-right"
                                        >1 month</span
                                    >
                                </div>
                            </div>
                        </div>
                        <div class="summary-block">
                            <div class="summary-content">
                                <div class="summary-head">
                                    <h5 class="summary-title">Total</h5>
                                </div>
                                <div class="summary-price">
                                    <p class="summary-text">$258 / mo</p>
                                    <span class="summary-small-text pull-right"
                                        >1 month</span
                                    >
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {};
    },
    methods: {
        async getCartItems() {
            let response = await axios.get("/checkout/get/items");
            console.log(response);
        },
    },
    mounted() {},
    created() {
        this.getCartItems();
    },
};
</script>
