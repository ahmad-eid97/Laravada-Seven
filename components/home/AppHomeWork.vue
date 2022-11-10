<template>
    <section class="work">
        <div class="row work-intro">
            <h2>Areas of Expertise</h2>
            <div class="seprator">
                <img src="https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/08/slant-separator.png" alt="">
            </div>
            <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas magna ligula, rutrum in venenatis aliquet, congue gravida lorem. Aliquam convallis orci a odio imperdiet, nec pharetra odio porta.
            </p>
        </div>
        <div class="row">
            <div class="col-sm-6 col-lg-4 work-item">
                <div class="inner">
                    <h3>Investment</h3>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas magna ligula, rutrum in venenatis aliquet, congue gravida lorem.
                    </p>
                </div>
            </div>
            <div class="col-sm-6 col-lg-4 work-item" style="margin-top: 32px; ">
                <div class="inner" style="background-color: rgb(52, 41, 173)">
                    <h3>Financial Planning</h3>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas magna ligula, rutrum in venenatis aliquet, congue gravida lorem.
                    </p>
                </div>
            </div>
            <div class="col-sm-6 col-lg-4 work-item">
                <div class="inner">
                    <h3>Debt Help</h3>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas magna ligula, rutrum in venenatis aliquet, congue gravida lorem.
                    </p>
                </div>
            </div>
            <div class="col-sm-6 col-lg-4 work-item">
                <div class="inner" style="background-color: rgb(52, 41, 173)">
                    <h3>Retirement</h3>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas magna ligula, rutrum in venenatis aliquet, congue gravida lorem.
                    </p>
                </div>
            </div>
            <div class="col-sm-6 col-lg-4 work-item" style="margin-top: 32px; ">
                <div class="inner">
                    <h3>Mortgage Advice</h3>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas magna ligula, rutrum in venenatis aliquet, congue gravida lorem.
                    </p>
                </div>
            </div>
            <div class="col-sm-6 col-lg-4 work-item">
                <div class="inner" style="background-color: rgb(52, 41, 173)">
                    <h3>General Advice</h3>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas magna ligula, rutrum in venenatis aliquet, congue gravida lorem.
                    </p>
                </div>
            </div>
        </div>
        <div class="row justify-content-center text-slice" style="margin-top: 78px">
            <p class="text-center">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas magna ligula, rutrum in venenatis aliquet, congue gravida lorem. Aliquam convallis orci a odio imperdiet, nec pharetra odio porta.
            </p>
            <a href="#" class="btn col-auto">REQUEST CALLBACK</a>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppHomeWork',
    data() {
        return {
            
        }
    }
}
</script>
<style lang="scss">
    .work {
        padding-top: 8%;
        margin-top: 0px;
        padding-right: 30px;
        padding-bottom: 8%;
        margin-bottom: 0px;
        padding-left: 30px;
    }
    .work-intro {
        margin-left: 24px;
        margin-right: 24px;
        min-height: 1px;
        padding-bottom: 0px;
        padding-left: 160px;
        padding-right: 160px
    }

    @include md {
        .work-intro {
            margin-left: 24px;
            margin-right: 24px;
            min-height: 1px;
            padding-bottom: 0px;
            padding-left: 0;
            padding-right: 0
        }
    }

    .work-intro h2 {
        margin-bottom: 15px;
        margin-top: 15px;
        color: rgb(33, 41, 52);
        font-size: 35px;
        font-weight: 800;
        letter-spacing: -1px;
        line-height: 42px;
        text-align: center;
    }
    .work-intro .seprator {
        text-align: center;
    }
    .work-intro .seprator img{
        width: 70px;
        margin-top: 5px;
        margin-bottom: 20px;
    }
    .work-intro p{
        margin-bottom: 20px;
        color: rgb(74, 78, 87);
        font-size: 16px;
        font-weight: 400;
        line-height: 29px;
        text-align: center;
    }
    .work .work-item{
        margin-bottom: 20px
    }
    .work .work-item .inner{
        margin-left: 24px;
        margin-right: 24px;
        padding-bottom: 25px;
        padding-left: 30px;
        padding-right: 30px;
        padding-top: 45px;
        background-color: rgb(83, 94, 229);
        border-radius: 60px 12px 60px 12px;
        text-align: center;
    }
    .work .work-item .inner h3{
        color: rgb(255, 255, 255);
        font-size: 20px;
        line-height: 26px;
        margin: 15px 0;
        font-weight: 900;
    }
    .work .work-item .inner p{
        color: rgb(255, 255, 255);
        font-size: 14px;
        line-height: 26px;
        margin: 0 0 20px;
        font-weight: 700;
    }
    .work .btn {
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
    .work .btn:hover {
        color: rgb(255, 255, 255);
        background-color: rgb(83, 94, 229);
        border: none;
    }

    .text-slice {
        padding: 0 160px;
    }

    @include md {
        .text-slice {
            padding: 0 20px;
        }
    }
</style>