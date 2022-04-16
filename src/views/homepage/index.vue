<template>
    <div class="container">
        <div class="banner">
            <el-image fit="cover" class="image" :src="require('@/assets/images/banner1.png')"></el-image>
        </div>
        <div class="content">
            <div class="detail">
                <div class="idea">
                    <div class="nav">
                        <div class="left">
                            <div class="triangle"></div>
                            <div>企業の理念</div>
                        </div>
                        <router-link to="/enterprise">
                            <div class="jump"></div>
                        </router-link>
                    </div>
                    <div class="view">
                        <img src="../../assets/images/drawing1.png" alt />
                    </div>
                    <div class="introduce">
                        <div></div>
                        <div>内外の法およびその精神を遵守し、人材育成、サービス向上。国内･外資企業の国際活動をサポートし，国際的な経済文化交流の発展に努めます。</div>
                    </div>
                </div>
                <div class="business">
                    <div class="nav">
                        <div class="left">
                            <div class="triangle"></div>
                            <div>主な事業内容</div>
                        </div>
                        <router-link to="/business">
                            <div class="jump"></div>
                        </router-link>
                    </div>
                    <div class="introduce" v-for="(item, index) in list" :key="index">
                        <div>
                            <div class="item">
                                <img :src="item.icon" alt />
                                <div class="text">{{ item.title }}</div>
                            </div>
                            <div class="businessDetail">{{ item.content }}</div>
                        </div>
                    </div>
                </div>
                <div class="warehouse">
                    <div class="nav">
                        <div class="left">
                            <div class="triangle"></div>
                            <div>倉庫作業</div>
                        </div>
                        <router-link to="/warehouse">
                            <div class="jump"></div>
                        </router-link>
                    </div>
                    <div class="view">
                        <img src="../../assets/images/drawing2.png" alt />
                    </div>
                </div>
            </div>
            <div class="address">
                <div class="linear">
                    <div class="left">
                        <div class="triangle"></div>
                        <div>事業所案内</div>
                    </div>
                    <router-link to="/enterprise">
                        <div class="jump"></div>
                    </router-link>
                </div>
                <div class="maps">
                    <div class="item" v-for="(map, index) in maps" :key="index">
                        <Gmap 
                            :id="'home' + index" 
                            :lat="map.mapCenter.lat" 
                            :lng="map.mapCenter.lng" 
                            height="145px" 
                        />
                        <div class="title">{{ map.title }}</div>
                        <div>〒 {{ map.code }}</div>
                        <div>{{ map.address }}</div>
                        <div v-if="map.TEL"><span>TEL：</span>{{ map.TEL }}</div>
                        <div v-if="map.FAX"><span>FAX：</span>{{ map.FAX }}</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Gmap from '@/components/Gmap/index.vue';
export default {
    components: {
        Gmap
    },
    data() {
        return {
            list: [
                {
                    icon: require('../../assets/images/iconHouse.png'),
                    title: 'ロジスティクス',
                    content: '標準サービス　デバンニング　保管　梱包　商品ラベル貼付　出荷'
                },
                {
                    icon: require(`../../assets/images/iconOnline.png`),
                    title: 'ネットショップ（EC販売）の運営サポート',
                    content: '商品・在庫・お届け・初期不良などのお問合せに対して、メール・電話対応'
                },
                {
                    icon: require(`../../assets/images/iconDeclare.png`),
                    title: 'コンテナ（船便）　通関代行サポート',
                    content: '通関手続きを代行し、荷物卸までサポート'
                },
                {
                    icon: require(`../../assets/images/iconMarketshop.png`),
                    title: '市場マーケティング・リサーチ',
                    content: '商品の特長をしっかりと提案し、お客様の調査ニーズに対し共に市場開拓する'
                },
            ],
            maps: [
                {
                    mapCenter: {lng: 139.5865982313701, lat: 35.7439796766915},
                    title: '本社',
                    code: '178-0063',
                    address: '東京都練馬区東大泉5-21-10',
                    TEL: '03-6323-5070',
                    FAX: '03-6323-5070'
                },
                {
                    mapCenter: {lng: 135.55761536953196, lat: 34.5259133765727},
                    title: '大阪支店',
                    code: '589-0001',
                    address: '大阪府大阪狭山市東野西3-746',
                    TEL: '0723-49-4939',
                    FAX: '0723-49-4941'
                },
                {
                    mapCenter: {lng: 135.54033268457127, lat: 34.540540658723806},
                    title: '堺井上倉庫',
                    code: '599-8112',
                    address: '大阪府堺市日置荘原寺町471-1',
                    TEL: '072-294-6355',
                    FAX: '072-294-6338'
                },
                {
                    mapCenter: {lng: 135.51624344039288, lat: 34.52311702784362}, 
                    title: '堺福田倉庫',
                    code: '599-8241',
                    address: '大阪府堺市中区福田701-1',
                    TEL: '0722-89-8396',
                    FAX: ''
                },
                {
                    mapCenter: {lng: 135.54812398457173, lat: 34.562228022178076}, 
                    title: '松原倉庫',
                    code: '580-0014',
                    address: '大阪府松原市岡7-238',
                    TEL: '0722-89-6796',
                    FAX: ''
                }
            ],
        }
    },
    mounted() {
        
    },
    methods: {
        
    }
}
</script>

<style lang="scss" scoped>
.container {
    position: relative;
    .banner {
        width: 100%;
        .image {
            width: 100%; 
            height: 503px;
        }
    }

    .content {
        width: 1200px;
        margin: 0 auto;
        .detail {
            padding-top: 26px;
            display: flex;
            justify-content: space-between;
            .idea {
                .nav {
                    width: 358px;
                    height: 37px;
                    background-image: linear-gradient(0deg,
                        #4f3d8e 0%,
                        #5a489c 13%,
                        #6552a9 50%,
                        #5a489c 89%,
                        #4f3d8e 100%
                    ), linear-gradient(#262626, #262626);
                    display: flex;
                    justify-content: space-between;
                    padding-left: 8px;
                    padding-right: 13px;
                    margin-bottom: 19px;
                    align-items: center;
                    font-size: 16px;
                    font-weight: normal;
                    font-stretch: normal;
                    color: #ffffff;

                    .left {
                        display: flex;
                        align-items: center;

                        .triangle {
                            width: 0;
                            height: 0;
                            border: 6px solid;
                            padding-right: 10px;
                            border-color: transparent transparent transparent #ffffff;
                        }
                    }
                }

                .introduce {
                    font-family: SourceHanSansCN-Regular;
                    font-size: 14px;
                    line-height: 25px;
                    line-height: 2;
                    color: #666666;
                    div{
                        &:nth-child(1){
                            width: 55px;
                            height: 54px;
                            background-image: url(../../assets/images/iconLogo.png);
                            background-repeat: no-repeat;
                            background-size: 100%;
                            margin-right: 20px;
                            float: left;
                        }
                        &:nth-child(2){
                            width: 355px;
                            height: 88px;
                        }
                    }
                }
            }

            .business {
                .nav {
                    width: 358px;
                    height: 37px;
                    background-image: linear-gradient(0deg,
                            #4f3d8e 0%,
                            #5a489c 13%,
                            #6552a9 50%,
                            #5a489c 89%,
                            #4f3d8e 100%),
                        linear-gradient(#262626, #262626);
                    display: flex;
                    justify-content: space-between;
                    padding-left: 8px;
                    padding-right: 13px;
                    margin-bottom: 9px;
                    align-items: center;
                    font-size: 16px;
                    color: #ffffff;

                    .left {
                        display: flex;
                        align-items: center;

                        .triangle {
                            width: 0;
                            height: 0;
                            border: 6px solid;
                            padding-right: 10px;
                            border-color: transparent transparent transparent #ffffff;
                        }
                    }
                }

                .introduce {
                    width: 360px;
                    border-bottom: 1px solid #dfdfdf;
                    padding: 10px 0;
                    &:nth-child(1) {
                        padding: unset;
                        padding-bottom: 10px;
                    }
                    &:nth-child(5) {
                        border: none;
                    }
                    .item {
                        display: flex;
                        align-items: center;
                        padding-bottom: 10px;

                        img {
                            width: 17px;
                            height: 17px;
                            margin-right: 15px;
                        }

                        .text {
                            font-size: 16px;
                            font-weight: bolder;
                            color: #2c2c2c;
                        }
                    }
                    .businessDetail {
                        font-family: SourceHanSansCN-Regular;
                        font-size: 14px;
                        font-weight: normal;
                        font-stretch: normal;
                        line-height: 21px;
                        color: #666666;
                    }
                }
            }

            .warehouse {
                .nav {
                    width: 358px;
                    height: 37px;
                    background-image: linear-gradient(0deg,
                            #4f3d8e 0%,
                            #5a489c 13%,
                            #6552a9 50%,
                            #5a489c 89%,
                            #4f3d8e 100%),
                        linear-gradient(#262626, #262626);

                    display: flex;
                    justify-content: space-between;
                    padding-left: 8px;
                    padding-right: 13px;
                    margin-bottom: 19px;
                    align-items: center;
                    font-size: 16px;
                    font-weight: normal;
                    font-stretch: normal;
                    color: #ffffff;

                    .left {
                        display: flex;
                        align-items: center;

                        .triangle {
                            width: 0;
                            height: 0;
                            border: 6px solid;
                            padding-right: 10px;
                            border-color: transparent transparent transparent #ffffff;
                        }
                    }
                }
            }
        }

        .address {
            .linear {
                width: 1199px;
                height: 37px;
                background-image: linear-gradient(0deg,
                        #4f3d8e 0%,
                        #5a489c 13%,
                        #6552a9 50%,
                        #5a489c 89%,
                        #4f3d8e 100%),
                    linear-gradient(#262626, #262626);
                display: flex;
                justify-content: space-between;
                padding-left: 8px;
                padding-right: 13px;
                margin-bottom: 9px;
                margin-top: 30px;
                align-items: center;
                font-size: 16px;
                color: #ffffff;

                .left {
                    display: flex;
                    align-items: center;

                    .triangle {
                        width: 0;
                        height: 0;
                        border: 6px solid;
                        padding-right: 10px;
                        border-color: transparent transparent transparent #ffffff;
                    }
                }
            }

            .maps {
                display: flex;
                justify-content: space-between;
                margin-bottom: 43px;
                .item {
                    width: 233px;

                    .title {
                        font-size: 16px;
                        font-weight: bolder;
                        color: #333333;
                        padding-top: 14px;
                        padding-bottom: 15px;
                    }

                    div {
                        color: #787878;
                        font-family: SourceHanSansCN-Regular;
                        font-size: 14px;
                        line-height: 22px;
                        span {
                            display: inline-block;
                            width: 38px;
                        }
                    }
                }
            }
        }
    }
    .jump {
        width: 8px;
        height: 8px;
        border-top: 2px solid #fff;
        border-right: 2px solid #fff;
        transform: rotate(45deg);
    }
}
</style>