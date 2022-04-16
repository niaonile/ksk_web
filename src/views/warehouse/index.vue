<template>
    <div class="container">
        <div class="banner">
            <el-image fit="cover" class="image" :src="require('@/assets/images/banner2.png')"></el-image>
            <div class="imgText">
                <el-image fit="none" :src="require('@/assets/images/banner2_text.png')"></el-image>
            </div>
        </div>
        <div class="content">
            <Sidebar />
            <div class="main">
                <div class="link">
                    <router-link to="/index">有限会社ケイ・エス・ケイ</router-link>>
                    <router-link to="/enterprise">トップページ</router-link>>
                    <router-link to>ロジスティクス 専門</router-link>
                </div>
                <div class="line"></div>
                <div class="logistics">
                    <img src="../../assets/images/bluehouse.png" />
                    <div>ロジスティクス 専門</div>
                </div>
                <div class="banners">
                    <img src="../../assets/images/img3.png" style="width: 100%" />
                </div>
                <div class="linear">
                    <div class="text">標準サービス</div>
                </div>
                <div class="modules">
                    <div class="item" v-for="(item) in list" :key="item.index">
                        <div class="icon">
                            <img :src="item.img" />
                        </div>
                        <div class="name">{{ item.title }}</div>
                    </div>
                </div>
                <div class="servicesTitle">
                    <div>オプションサービス</div>
                </div>
                <div class="services">
                    <div class="service" v-for="(serve) in services" :key="serve.index">
                        <img :src="serve.img">
                        <div class="serveTitle">
                            {{serve.title}}
                        </div>
                    </div>
                </div>
                <div class="linear">
                    <div class="text">物流代行の流れ</div>
                </div>
                <div class="flowsheets">
                    <div class="flowsheet">
                        <img src="../../assets/images/01.png">
                        <img src="../../assets/images/01s.png" />
                        <div>お問い合わせ</div>
                    </div>
                    <div class="flowsheet">
                        <img src="../../assets/images/02.png">
                        <img src="../../assets/images/02s.png" />
                        <div>ヒアリング</div>
                    </div>
                    <div class="flowsheet">
                        <img src="../../assets/images/03.png">
                        <img src="../../assets/images/03s.png" />
                        <div>見学</div>
                    </div>
                    <div class="flowsheet">
                        <img src="../../assets/images/04.png">
                        <img src="../../assets/images/04s.png" />
                        <div>お打ち合わせ</div>
                    </div>
                    <div class="flowsheet">
                        <img src="../../assets/images/05.png">
                        <img src="../../assets/images/05s.png" />
                        <div>見積書提出</div>
                    </div>
                    <div class="flowsheet">
                        <img src="../../assets/images/06.png">
                        <img src="../../assets/images/06s.png" />
                        <div>アカウントをご登録</div>
                    </div>
                    <div class="flowsheet">
                        <img src="../../assets/images/07.png">
                        <img src="../../assets/images/07s.png" />
                        <div>商品入庫</div>
                    </div>
                    <div class="flowsheet">
                        <img src="../../assets/images/08.png">
                        <img src="../../assets/images/08s.png" />
                        <div>処理代行サービスのスタート</div>
                    </div>
                </div>
                <div class="linear">
                    <div class="text">对应商品</div>
                </div>
                <div class="commodities">
                    <div class="commodityOne">
                        <div class="img">
                            <img src="../../assets/images/commodit1.png">
                        </div>
                        <div>服装</div>
                    </div>
                    <div class="commodityOne">
                        <div class="img">
                        <img src="../../assets/images/commodit2.png">
                        </div>
                        <div>化粧品</div>
                    </div>
                    <div class="commodityTwo">
                        <div class="commodityTwos">
                            <div class="img">
                            <img src="../../assets/images/commodit3.png">
                            </div>
                            <div>おもちゃ</div>
                        </div>
                        <div class="commodityTwos">
                            <div class="img">
                            <img src="../../assets/images/commodit4.png">
                            </div>
                            <div>スポーツ用品</div>
                        </div>
                    </div>
                    <div class="commodityOne">
                        <div class="img">
                        <img src="../../assets/images/commodit5.png">
                        </div>
                        <div>電子製品</div>
                    </div>
                    <div class="commodityTwo">
                        <div class="commodityTwos">
                            <div class="img">
                            <img src="../../assets/images/commodit6.png">
                            </div>
                            <div>日用品</div>
                        </div>
                        <div class="commodityTwos">
                            <div class="img">
                            <img src="../../assets/images/commodit7.png">
                            </div>
                            <div>家電</div>
                        </div>
                    </div>
                    <div class="commodityOne">
                        <div class="img">
                        <img src="../../assets/images/commodit8.png">
                        </div>
                        <div>家具</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { Sidebar } from "../../components"
export default {
    components: {
        Sidebar
    },
    data() {
        return {
            list: [
                {
                    img: require("../../assets/images/Unpacking.png"),
                    title: "デバンニング"
                },
                {
                    img: require("../../assets/images/safekeeping.png"),
                    title: "保管"
                },
                {
                    img: require("../../assets/images/MaterialList.png"),
                    title: "梱包"
                },
                {
                    img: require("../../assets/images/Label.png"),
                    title: "商品ラベル貼付"
                },
                {
                    img: require("../../assets/images/Shipment.png"),
                    title: "出荷"
                },
            ],
            services:[
                {
                    img: require("../../assets/images/check.png"),
                    title: "品質検品"
                },
                {
                    img: require("../../assets/images/tip.png"),
                    title: "領収書封入"
                },
                {
                    img: require("../../assets/images/pack.png"),
                    title: "梱包資材指定"
                },
                {
                    img: require("../../assets/images/photoshop.png"),
                    title: "撮影・採寸"
                },
                {
                    img: require("../../assets/images/send.png"),
                    title: "配達不能返送対応"
                },
                {
                    img: require("../../assets/images/return.png"),
                    title: "購入者様からの返品対応"
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    position: relative;
    .banner {
        position: relative;
        display: flex;
        justify-content: center;
        .image {
            width: 100%; 
        }
        .imgText {
            width: 1200px;
            height: 60px;
            position: absolute;
            top: 130px;
        }
    }
    .content {
        width: 1200px;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        .main {
            margin-left: 22px;
            .link {
                font-family: SourceHanSansCN-Regular;
                font-size: 14px;
                line-height: 25px;
                letter-spacing: 1px;
                color: #666666;
                margin-bottom: 10px;
                margin-top: 26px;
            }
            .line {
                margin-left: 2px;
                margin: 18px 0 7px 0;
                height: 1px;
                border-bottom: solid 1px #dfdfdf;
            }
            .logistics {
                display: flex;
                align-items: center;
                padding: 14px 0 25px 0;
                font-size: 20px;
                font-weight: bolder;
                color: #6552a9;
                img{
                    width: 30px;
                    height: 30px;
                }
            }
            .banner {
                height: 225px;
                margin-bottom: 18px;
                img {
                    width: 100%;
                }
            }
            .modules {
                display: flex;
                align-items: center;
                justify-content: space-around;
                .item {
                    width: 20%;
                    padding: 40px 0;
                    .icon {
                        width: 53px;
                        height: 47px;
                        margin: auto;
                        display: flex;
                        justify-content: space-around;
                    }
                    .name {
                        margin-top: 20px;
                        text-align: center;
                    }
                }
            }
            .servicesTitle{
                font-size: 14px;
                font-weight: bolder;
                line-height: 25px;
                letter-spacing: 1px;
                color: #333333;
                padding-bottom: 15px;
                border-bottom: solid 1px #dfdfdf;;
            }
            .services{
                display: flex;
                flex-wrap: wrap;
                justify-content: space-between;
                margin-bottom: 30px;
                .service{
                    width: 257px;
                    height: 33px;
                    border-radius: 3px;
                    margin-top: 10px;
                    padding-left: 25px;
                    display: flex;
                    align-items: center;
                    background-color: rgba(101, 81, 168, 0.1);
                    .serveTitle{
                        min-width: 130px;
                    }
                    img{
                        width: 17px;
                        height: 17px;
                        margin-right: 15px;
                    }
                }
            }
            .linear {
                margin: 15px 0;
                border-radius: 5px;
                text-align: center;
                background-color: #6551a8;
                .text {
                    padding: 16px 0;
                    font-size: 18px;
                    font-weight: bolder;
                    letter-spacing: 1px;
                    color: #ffffff;
                }
            }
            .flowsheets {
                display: flex;
                flex-wrap: wrap;
                justify-content: space-between;
                padding-top: 11px;
                padding-bottom: 13px;
                .flowsheet{
                    text-align: center;
                    margin-bottom: 8px;
                    position: relative;
                    font-weight: bolder;
                    background-color: #f7f7f7;
                    img{
                        &:nth-child(1){
                            position: absolute;
                            left: 8px;
                            top: 8px;
                            width: 40px;
                            height: 30px;
                            font-size: 40px;
                            font-weight: bold;
                            line-height: 22px;
                            color: #6551a8;
                            opacity: 0.8;
                        }
                    }
                    div{
                        padding: 15px 0;
                    }
                }
            }
            .commodities{
                display: flex;
                flex-wrap: wrap;
                justify-content: space-between;
                margin-bottom: 23px;
                text-align: center;
                font-family: SourceHanSansCN-Regular;
                font-size: 16px;
                color: #ffffff;
                .commodityOne{
                    width: 222px;
                    height: 128px;
                    background-image: linear-gradient(143deg, 
                        #29ade0 0%, 
                        #2f76e0 100%);
                    border-radius: 3px;
                    border: solid 1px #dcdcdc;
                    margin-bottom: 8px;
                    .img{
                        padding-top: 30px;
                        padding-bottom: 15px;
                    }
                }
                .commodityTwo{
                    width: 340px;
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    margin-bottom: 8px;
                    .commodityTwos{
                        width: 340px;
                        height: 61px;
                        background-image: linear-gradient(143deg, 
                            #29ade0 0%, 
                            #2f76e0 100%);
                        border: solid 1px #dcdcdc;
                        border-radius: 3px;
                        display: flex;
                        align-items: center;
                        padding-left: 90px;
                        .img{
                            display: flex;
                            align-items: center;
                            justify-content: center;
                            width: 45px;
                            margin-right: 30px;
                        }
                    }
                }
            }
        }
    }
}
</style>