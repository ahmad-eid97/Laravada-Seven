<template>
    <div class="featured">
        <h2>
            As Featured In
        </h2>
        <div class="row mx-0">
            <div class="col-sm-6 col-md-6 col-lg-3 brand">
                <img src="https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/09/internet-times.png" alt="">
            </div>
            <div class="col-sm-6 col-md-6 col-lg-3 brand">
                <img src="https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/09/money-magazine.png" alt="">
            </div>
            <div class="col-sm-6 col-md-6 col-lg-3 brand">
                <img src="https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/09/netcash.png" alt="">
            </div>
            <div class="col-sm-6 col-md-6 col-lg-3 brand">
                <img src="https://avada.theme-fusion.com/financial-advisor/wp-content/uploads/sites/145/2020/09/ilifestyle.png" alt="">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AppHomeFeatured',
    data() {
        return {

        }
    }
}
</script>
<style>
    .featured {
        padding-top: 50px;
        margin-top: 0px;
        padding-right: 30px;
        padding-bottom: 0;
        margin-bottom: 0px;
        padding-left: 30px;
        text-align: center;
        
    }
    .featured h2 {
        color: rgb(33, 41, 52);
        font-size: 35px;
        font-weight: 900;
        line-height: 42px;
        letter-spacing: -1px;
        margin-bottom: 20px;
    }
    .featured .brand {
        /* margin-bottom: 20px;
        margin-left: 24px;
        margin-right: 24px; */
        /* width: 450px; */
        height: 165px;
        filter: opacity(40%);
    }
    .featured .brand img {
        max-width: 100%;
    }
    .featured .brand:hover {
        filter: opacity(100%);
    }
    
</style>