<template>
    <div class="sidebar">
        <div class="header">
            <img src="../../assets/images/logo.png" alt="">
            <div class="title">有限会社 ケイ・エス・ケイ</div>
        </div>
        <div class="body">
            <div class="contact">
                大阪府大阪狭山市東野西3-746
            </div>
            <div class="contact">
                TEL：0723-49-4939 
            </div>
            <div class="contact">
                FAX：0723-49-4941
            </div>
            <div class="contact">
                メールアドレス：info@kskjp.com
            </div>
            <div class="contact">
                https://www.kskjp.com
            </div>
        </div>
        <div class="footer">
            <div class="title">
                <div class="icon">
                    <img src="../../assets/images/whiteWarehouse.png" alt="">
                </div>
                <div class="text">
                    お問い合わせ
                </div>
                <div class="contact">
                    <div class="phone">電話番号</div>
                    <div class="number">0723－49－4939</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.sidebar {
    width: 360px;
    .header {
        display: flex;
        align-items: center;
        flex-direction: column;
        img {
            width: 102px;
            height: 102px;
            margin-top: 37px;
            margin-bottom: 11px;
        }
        .title {
            color: #0d0d0d;
            font-size: 24px;
            font-weight: bold;
        }
    }
    .body {
        margin: 0 15px;
        font-size: 14px;
        line-height: 22px;
        color: #555555;
        margin-top: 28px;
        margin-bottom: 23px;
        .contact {
            font-size: 14px;
            color: #555555;
            padding: 18px 0 17px 5px;
            border-top: 1px solid #ccc;
            &:last-child {
                border-bottom: 1px solid #ccc;
            }
        }
    }
    .footer {
        width: 360px;
        height: 330px;
        background-color: #707070;
        background-image: url(../../assets/images/bg3.png);
        .title {
            margin-left: 20px;
            padding-top: 53px;
            .icon {
                margin-left: 8px;
                margin-bottom: 26px;
            }
            .text {
                margin-left: 2px;
                margin-bottom: 68px;
                height: 30px;
                font-size: 30px;
                font-weight: bold;
                line-height: 46px;
                color: #ffffff;
            }
            .contact {
                .phone {
                    height: 19px;
                    font-size: 18px;
                    font-weight: bold;
                    color: #ffffff;
                }
                .number {
                    margin-left: 2px;
                    margin-top: 10px;
                    font-size: 25px;
                    font-weight: bold;
                    color: #ffffff;
                }
            }
        }
    }
    
}
</style>