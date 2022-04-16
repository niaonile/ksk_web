<template>
    <div class="header">
        <div class="box">
            <div>
                <img src="../../assets/images/ksk_logo.png" alt="">
            </div>
            <div class="contact">
                <div class="phone">
                    <img src="../../assets/images/colorphone.png" alt="">
                </div>
                <div class="number">0723－49－4939</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.header {
    background-color: #fff;
    .box{
        width: 1200px;
        height: 94px;
        margin: 0 auto;
        padding: 0 30px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        .contact{
            display: flex;
            align-items: center;
            .phone{
                width: 40px;
                height: 40px;
                margin-right: 10px;
                border: 1px solid #4f3c8e;
                border-radius: 50%;
                display: flex;
                align-items: center;
                justify-content: center;
            }
            .number{
                font-size: 25px;
                font-weight: bold;
                line-height: 16px;
                color: #4f3c8e;
            }
        }
    }
    
}
</style>