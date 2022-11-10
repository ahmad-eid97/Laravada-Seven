<template>
    <section class="intro">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-12 inner">
                    <h1>Get Your Money Working For You</h1>
                    <h2>Where & how to invest / Start on your path to</h2>
                    <p>
                        Specializing in smart investment and frugal financial planning and advice to give you the best possible outcomes both short term and long term throughout economic downturn.
                    </p>
                    <form class="intro-form">
                        <b-form-input
                            id="input-1"
                            type="tel"
                            placeholder="Telephone Number"
                            >
                        </b-form-input>
                        <a href="#" class="btn col-12">REQUEST CALLBACK</a>
                    </form>
                    <p class="or">
                        <a href="#">Or click here to book your call</a>
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppHomeIntro',
    data() {
        return {

        }
    }
}
</script>
<style lang="scss">
    .intro {
        background-color: var(--awb-color7);
        background-position: left top;
        background-repeat: no-repeat;
        border-width: 0px;
        border-color: var(--awb-color2);
        border-style: solid;
        background-size: cover;
        background-image: url("https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/08/homepage-hero-background.svg");
        padding-top: 40px;
        margin-top: 0px;
        padding-right: 30px;
        padding-bottom: 80px;
        margin-bottom: 0px;
        padding-left: 30px;
        text-align: center;
    }

    .intro .container {
        /* padding: 0 77px; */
    }

    .intro .inner {
        padding-top: 100px !important;
        padding-right: 100px !important;
        padding-bottom: 100px !important;
        padding-left: 100px !important;
        background-color: rgba(0, 0, 0, 0.1);
        border-radius: 12px 12px 12px 12px;
    }

    @include sm {
        .intro .inner {
            padding-right: 20px !important;
            padding-left: 20px !important;
        }
    }
    
    .intro h1 {
        font-weight: 900;
        margin: 10px 0 15px;
        font-size: 45px;
        letter-spacing: -1px;
        color: #fff;
        line-height: 52px;
        text-align: center;
    }

    @include xs {
        .intro h1 {
            font-size: 30px;
            line-height: 40px;
        }
    }

    .intro h2 {
        font-weight: 800;
        margin: 10px 0 15px;
        font-size: 14px;
        color: rgba(255, 255, 255, 0.75);
        letter-spacing: 2px;
        line-height: 24px;
        text-align: center;
        text-transform: uppercase
    }
    .intro p {
        margin: 16px 0;
        text-align: center;
        font-size: 16px;
        line-height: 29px;
        text-transform: capitalize;
        color: #fff;
        font-weight: 700;
    }
    .intro-form {
        margin-top: 40px;
        background-color: rgb(52, 41, 173);
        border-radius: 8px;
        padding: 40px 50px 30px;
    }
    .intro-form input{
        background-color: rgb(255, 255, 255);
        border: 1px solid rgb(131, 139, 228);
        padding: 0 16px;
        height: 50px;
        font-size: 16px;
        font-weight: 700 !important;
        color: rgb(226, 226, 226) !important;
        margin: 15px 0;
    }
    .intro-form input:focus{
        box-shadow: none;
    }
    .intro-form input::placeholder{
        color: rgb(226, 226, 226) !important;
    }
    .intro .btn {
        padding: 13px 29px;
        color: rgb(61, 61, 61);
        margin: 15px 0;
        background-color: rgb(81, 229, 165);
        border-radius: 6px;
        letter-spacing: 2px;
        border: none;
        font-size: 14px;
        line-height: 18px;
        font-weight: 800;
    }
    .intro .btn:hover {
        color: rgb(255, 255, 255);
        background-color: rgb(83, 94, 229);
        border: none;
    }
    
    .intro .or {
        margin: 32px 0 16px;
    }
    .intro .or a {
        color: rgb(255, 255, 255);
        font-size: 16px;
        font-weight: 800;
        line-height: 28.8px;
        text-align: center;
        text-decoration: none;
        margin: 32px 0 16px;
    }
</style>