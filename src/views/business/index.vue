<template>
    <div class="container">
        <div class="banner">
            <el-image fit="cover" class="image" :src="require('@/assets/images/banner5.png')"></el-image>
            <div class="imgText">
                <el-image fit="none" :src="require('@/assets/images/banner5_text.png')"></el-image>
            </div>
        </div>
        <div class="content">
            <Sidebar />
            <div class="main">
                <div class="link">
                    <router-link to="/index">有限会社ケイ・エス・ケイ</router-link>>
                    <router-link to="/enterprise">トップページ</router-link>>
                    <router-link to>事業内容</router-link>
                </div>
                <div class="line"></div>
                <div class="linear">
                    <div class="text">ネットショップ（EC販売）の運営サポート</div>
                </div>
                <div class="logos">
                    <div><img src="../../assets/images/logo1.png" alt=""></div>
                    <div><img src="../../assets/images/logo2.png" alt=""></div>
                    <div><img src="../../assets/images/logo3.png" alt=""></div>
                    <div><img src="../../assets/images/logo4.png" alt=""></div>
                </div>
                <div class="management">
                    <div>カスタマーサポート（商品・在庫・お届け・初期不良などのお問合せに対して、メール・電話対応）</div>
                    <div>オーダー管理サポート（注文内容確認から出荷データ送付など一連の業務）</div>
                    <div>物流代行（各運送会社と提携しより安い運賃で検品・梱包から発送まで全力でサポート）</div>
                    <div>Rakuten、Amazon ・Qoo10・Yahooなど EC モールにおいて、出店された企業様を中心にサポート実績がございます。</div>
                </div>
                <div class="linear">
                    <div class="text">コンテナ（船便）　通関代行サポート</div>
                </div>
                <div class="imgs">
                    <img src="../../assets/images/warehouses.png" alt="">
                </div>
                <div class="management">
                    <div>主に海外からの輸出を中心に通関手続きを代行し、荷物卸までサポート致します。</div>
                    <div>安心安全のお任せプランから申告内容のチェック、インボイスの作成及びチェックや、</div>
                    <div>税率の計算、諸々必要書類の作成もしくは内容チェックなどまで、</div>
                    <div>その他も困っていることあれば、いつでもお気軽にご相談ください。</div>
                </div>
                <div class="linear">
                    <div class="text">市場マーケティング・リサーチ</div>
                </div>
                <div class="module">
                    <div class="left">
                        市場の現状と規模に合わせて、商品を提案し、お客様のご希望に従って市場開拓することをサポート致します。海外製品・メーカーを熟知しているため、提携している海外優良な工場を繋げることも可能です。通販企業や小売業、家電メーカーの海外工場との取引や値段交渉など全てサポートいたします。＜小ロットからも対応可＞＜日本人スタッフが対応＞＜国内でのお打合せ可能＞＜仲介手数料一切不要＞OEM工場選定, OEM工場との交渉, 製品委託製造, 海外仕入れ等
                    </div>
                    <div class="right">
                        <div><img src="../../assets/images/hand.png" alt=""></div>
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
            .logos{
                display: flex;
                flex-wrap: wrap;
                justify-content: space-around;
            }
            .imgs {
               img {
                    width: 100%;
               }
            }
            .management{
                font-size: 14px;
                font-family: SourceHanSansCN;
                font-weight: 400;
                color: #666666;
                line-height: 30px;
                padding-top: 21px;
                padding-left: 10px;
                margin-bottom: 21px;
            }
            .module{
                display: flex;
                justify-content: space-between;
                margin-top: 11px;
                margin-bottom: 46px;
                .left{
                    width: 399px;
                    font-size: 14px;
                    font-family: SourceHanSansCN;
                    font-weight: 400;
                    color: #666666;
                    line-height: 30px;
                    padding-top: 10px;
                    padding-left: 10px;
                }
                .right{
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