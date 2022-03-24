<template>
    <div class="works">
        <div class="container my-5 p-4">
            <h1 class="text-center my-5">how it works</h1>
            <div class="row">
                <div class="col-sm-4">
                    <i class="fa-solid fa-car-side my-4"></i>
                    <h4 class="text-center my-3 w-75 m-auto">YOU TELL US WHAT IS WRONG</h4>
                    <p>
                        Tell us where you are based, what car you are experiencing issues with and what you think is
                        wrong (e.g., “my car is shaking” or “I need new brakes”) and we take care of the rest.
                    </p>
                </div>
                <div class="col-sm-4">
                    <i class="fa-solid fa-tag my-4"></i>
                    <h4 class="text-center my-3">
                        GET A FAIR & TRANSPARENT PRICE</h4>
                    <p>
                        All our mobile mechanics have agreed to honor the quotes we provide. This ensures that there
                        will be no need for negotiations or any last minute surprises.
                    </p>
                </div>
                <div class="col-sm-4">
                    <i class="fa-solid fa-calendar-plus my-4"></i>
                    <h4 class="text-center my-3">TELL US WHEN YOU ARE AVAILABLE</h4>
                    <p>
                        Select a time and place that works for you and provide payment information to book your service.
                        We support a number of online payment options.
                    </p>
                </div>
                <button class="btn btn-outline-primary rounded-pill mt-3">Request a quote</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style lang="scss" scoped>
    $tertiaryText: #fff;
    $secondaryBg: #003f88;

    .works {
        margin-top: 100px;

        .container {

            background: rgba($color: #00509d, $alpha: .5);
            border-radius: 20px;

            .btn-outline-primary {
                font-weight: bold;
                background-color: rgba($color: #00509d, $alpha: 1.0);
                color: $tertiaryText;
                border-radius: 10px;
                width: 180px;
                height: 60px;
                transition: 0.4s ease all;
                margin-inline: auto;



                &:hover {
                    background-color: transparent;
                    transition: 0.4s ease all;
                    color: rgba($color: #00509d, $alpha: .8);
                }

            }

            p {
                text-align: center;
                width: 85%;
                margin-inline: auto;
                font-size: 1.2em;
            }

            i {
                font-size: 3rem;
                margin-left: 120px;
                background: rgba($color: #00509d, $alpha: .8);
                padding: 20px;
                border-radius: 20px;
            }

            h1 {
                text-transform: uppercase;
            }
        }
    }
</style>