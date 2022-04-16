<template>
    <div class="container">
        <div class="banner">
            <el-image fit="cover" class="image" :src="require('@/assets/images/banner4.png')"></el-image>
            <div class="imgText">
                <el-image fit="none" :src="require('@/assets/images/banner4_text.png')"></el-image>
            </div>
        </div>
        <div class="content">
            <Sidebar />
            <div class="main">
                <div class="link">
                    <router-link to="/index">有限会社ケイ・エス・ケイ</router-link>>
                    <router-link to="/enterprise">トップページ</router-link>>
                    <router-link to>事業所案内</router-link>
                </div>
                <div class="line"></div>
                <div class="outline">
                    <div class="text">会社概要&事業所案内</div>
                </div>
                <div class="table">
                    <el-table :row-class-name="tableRowClassName" :show-header="false" :data="tableData"
                        style="width: 100%;">
                        <el-table-column prop="name" label="商号" width="130">
                        </el-table-column>
                        <!-- <el-table-column label="|" width="76" style="opacity:.5;background:#d4d4d4">|</el-table-column> -->
                        <el-table-column class="fontColor" prop="data" label="有限会社ケイ・エス・ケイ">
                        </el-table-column>
                    </el-table>
                </div>
                <div class="maps">
                    <div class="item" v-for="(map, index) in maps" :key="index">
                        <Gmap 
                            :id="'ent' + index" 
                            :lat="map.mapCenter.lat" 
                            :lng="map.mapCenter.lng" 
                            height="162px" 
                        />
                        <div class="title">{{ map.title }}</div>
                        <div>{{ map.code }}</div>
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
import { Sidebar } from "@/components";
import Gmap from '@/components/Gmap/index.vue';
export default {
    components: {
        Gmap,
        Sidebar
    },
    methods: {
        tableRowClassName({ row, rowIndex }) {
            if (rowIndex === 0) {
                return 'success-row';
            } else if (rowIndex === 2) {
                return 'success-row';
            } else if (rowIndex === 4) {
                return 'success-row';
            }
            return '';
        }
    },
    data() {
        return {
            tableData: [{
                name: '商号',
                data: '有限会社ケイ・エス・ケイ',
            }, {
                name: '創業',
                data: '1992年（平成4年）7月21日',
            }, {
                name: '資本金',
                data: '2,000万円',
            }, {
                name: '本社',
                data: '〒178-0063 東京都練馬区東大泉5-21-10',
            }, {
                name: '支社',
                data: '〒589-0001 大阪府大阪狭山市東野西3-746',
            }],
            maps: [
                {
                    mapCenter: {lng: 139.5865982313701, lat: 35.7439796766915},
                    title: '本社',
                    code: '〒178-0063',
                    address: ' 東京都練馬区東大泉5-21-10',
                    TEL: '03-6323-5070 ',
                    FAX: '03-6323-5070'
                },
                {
                    mapCenter: {lng: 135.55761536953196, lat: 34.5259133765727},
                    title: '大阪支店',
                    code: '〒589-0001',
                    address: '大阪府大阪狭山市東野西3-746',
                    TEL: '0723-49-4939',
                    FAX: '0723-49-4941'
                },
                {
                    mapCenter: {lng: 135.54033268457127, lat: 34.540540658723806},
                    title: '堺井上倉庫',
                    code: '〒599-8112',
                    address: '大阪府堺市日置荘原寺町471-1',
                    TEL: '072-294-6355',
                    FAX: '072-294-6338'
                },
                {
                    mapCenter: {lng: 135.51624344039288, lat: 34.52311702784362}, 
                    title: '堺福田倉庫',
                    code: '〒599-8241',
                    address: '大阪府堺市中区福田701-1',
                    TEL: '0722-89-8396',
                    FAX: ''
                },
                {
                    mapCenter: {lng: 135.54812398457173, lat: 34.562228022178076}, 
                    title: '松原倉庫',
                    code: '〒580-0014',
                    address: '大阪府松原市岡7-238',
                    TEL: '0722-89-6796',
                    FAX: ''
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
                font-weight: normal;
                font-stretch: normal;
                line-height: 25px;
                letter-spacing: 1px;
                color: #666666;
                margin-bottom: 10px;
                margin-top: 26px;
            }

            .line {
                margin-left: 2px;
                width: 808px;
                margin: 18px 0 16px 0;
                height: 1px;
                border-bottom: solid 1px #dfdfdf;
            }

            .outline {
                height: 20px;
                font-family: SourceHanSansCN-Bold;
                font-size: 20px;
                line-height: 22px;
                color: #6552a9;
                margin-bottom: 13px;
                .text {
                    font-weight: bolder;
                }
            }
            .table{
                ::v-deep.el-table{
                    .el-table__row{
                        td{
                            &:nth-child(1){
                                width: 27px;
                                height: 13px;
                                font-family: SourceHanSansCN-Regular;
                                font-size: 14px;
                                line-height: 25px;
                                letter-spacing: 1px;
                                color: #333333;
                                div{
                                    border-right: 1px solid #D4D4D4;
                                }
                            }
                            &:nth-child(2){
                                width: 305px;
                                height: 16px;
                                padding-left: 70px;
                                font-family: SourceHanSansCN-Regular;
                                font-size: 16px;
                                line-height: 25px;
                                letter-spacing: 1px;
                                color: #604da2;
                            }
                        }
                    }
                    .success-row {
                        background: #f5f5f5;
                    }
                }
            }

            .maps {
                display: flex;
                flex-wrap: wrap;
                justify-content: space-between;
                margin-top: 28px;
                margin-bottom: 31px;
                &:after {
                    content: "";
                    width: 261px;
                }

                .item {
                    width: 261px;
                    margin-bottom: 38px;

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

            .linear {
                // width: 806px;
                height: 51px;
                background-color: #6551a8;
                border-radius: 5px;
                display: flex;
                align-items: center;
                justify-content: center;
                margin-bottom: 16px;

                .text {
                    font-family: SourceHanSansCN-Bold;
                    font-size: 18px;
                    font-weight: normal;
                    font-stretch: normal;
                    line-height: 22px;
                    letter-spacing: 0px;
                    color: #ffffff;
                }
            }

            .logos {
                display: flex;
                flex-wrap: wrap;
                justify-content: space-around;
            }

            .management {
                font-family: SourceHanSansCN-Regular;
                font-size: 14px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 30px;
                letter-spacing: 1px;
                color: #666666;
                padding-top: 21px;
                margin-bottom: 21px;
            }

            .module {
                display: flex;
                justify-content: space-between;
                margin-top: 11px;
                margin-bottom: 46px;

                .left {
                    font-family: SourceHanSansCN-Regular;
                    font-size: 14px;
                    font-weight: normal;
                    font-stretch: normal;
                    line-height: 30px;
                    letter-spacing: 1px;
                    color: #666666;
                    padding-right: 29px;
                }

                .right {
                    width: 372px;
                    height: 244px;
                    background-color: #6551a8;
                    border-radius: 5px;
                }
            }

        }
    }
}
</style>