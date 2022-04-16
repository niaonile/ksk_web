<template>
  <div class="container">
    <div class="header">
      <div class="head">
        <div class="left">
          <img src="../../assets/images/logo.png" alt />
          <div>有限会社 ケイ・エス・ケイ</div>
        </div>
        <div class="right">
          <img src="../../assets/images/colorphone.png" alt />
          <div>400-1234-234</div>
        </div>
      </div>
      <div class="nav">
        <div class="select">
          <div class="item">
            <router-link to="/business">
              事業内容事業所案内
            </router-link>
          </div>丨
          <div class="item">
            <router-link to="/warehouse">
              外倉庫
            </router-link>
          </div>丨
          <div class="item">
            <router-link to="/enterprise">
              企業情报
            </router-link>
          </div>丨
          <div class="item">
            <router-link to="/index">
              トップページ
            </router-link>
          </div>
        </div>
      </div>
      <div class="banner">
        <div class="phone">
          <img src="../../assets/images/phone.png" alt="">
          <div>400-1234-234</div>
        </div>
      </div>
      <div class="service">
        <div class="serve" v-for="(serve) in service" :key="serve.index">
          <router-link :to="serve.url">
            <div class="icon">
              <img :src="serve.icon" alt="">
            </div>
            <div class="serviceName">{{serve.title}}</div>
            <div class="serviceText">{{serve.text}}</div>
          </router-link>
        </div>
        <div class="serveScope">
          <div class="title">SERVICE SCOPE</div>
          <div class="text">サービス範囲</div>
        </div>
      </div>
    </div>

    <div class="body">
      <div class="total">
        <div class="title">会社概要</div>
        <div class="text">内外の法およびその精神を遵守し、人材育成、サービス向上.</div>
        <div class="text">国内･外資企業の国際活動をサポートし，国際的な経済文化交流の発展に努めます</div>
        <div class="img">
          <img src="../../assets/images/totalview.png" alt="">
        </div>
      </div>
      <div class="house">
        <div class="houseview">
          <div class="left">
            <div class="content">
              <el-carousel :interval="5000" indicator-position="none" arrow="never" height="967px" ref="cardShow">
                <el-carousel-item v-for="(carousel) in carousels" :key="carousel.index">
                  <h3>
                    <div class="carouselName">
                      {{ carousel.name }}
                      <router-link :to="carousel.url">
                        <img src="../../assets/images/arrow.png" alt="">
                      </router-link>
                    </div>
                  </h3>
                  <div class="title">{{ carousel.baseTitle }}</div>
                  <div class="text">{{ carousel.baseText }}</div>
                  <div class="title">{{ carousel.optionTitle }}</div>
                  <div class="text">{{ carousel.optionText }}</div>
                </el-carousel-item>
              </el-carousel>
              <!-- <div class="indicator">
                <div :class="0?'indact isactive':'indact'" v-for="(indact) in indicator" :key="indact.index" @click="handleIndicat">
                  {{indact.name}}
                </div>
              </div> -->
              <div class="arrow">
                <div class="prev">
                  <img src="../../assets/images/left.png"  @click="arrowClick('prev')" />
                </div>
                <div class="next">
                  <img src="../../assets/images/right.png"  @click="arrowClick('next')" />
                </div>
              </div>
            </div>
            <img src="" alt="">
          </div>
          <div class="right">
            <!-- <img src="../../assets/images/houseview.png" alt=""> -->
          </div>
        </div>
        <div class="housemap">
          <div class="name">事業所案内</div>
          <div class="location">
            <div class="left">
              <div class="icon">
                <!-- map -->
              </div>
              <div class="title">本社</div>
              <div class="text">〒178-0063　東京都練馬区東大泉5-21-10</div>
              <div class="text">TEL：03-6323-5070 FAX：03-6323-5070</div>
            </div>
            <div class="right">
              <div class="item" v-for="(map) in maps" :key="map.index">
                <div class="icon">
                  <!-- map -->
                </div>
                <div class="title">{{map.title}}</div>
                <div class="text">〒{{map.text}}</div>
                <div class="text"><span>TEL:</span>{{map.telephone}}<span :class="map.FAX?'spanF':''" v-if="map.FAX?1:0">FAX:</span>{{map.FAX}}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="footer">
      <div class="foote">
        <div class="title">
          <img src="../../assets/images/iconLogo.png" alt="">
          <div class="name">有限会社 ケイ・エス・ケイ</div>
        </div>
        <div class="linear"></div>
        <div class="address">
          <div class="text">有限会社ケイ・エス・ケイ</div>
          <div class="text">〒178-0063 東京都練馬区東大泉5-21-10</div>
          <div class="text">TEL：03-6323-5070 FAX：03-6323-5070</div>
        </div>

      </div>
    </div>  </div>
</template>

<script>
import Footer from "../../components"
export default {
  components: {
    Footer,
},
  data() {
    return {
      service:[
        {
          url:'/index',
          icon:require('../../assets/images/blackhouse.png'),
          title:'海外倉庫',
          text:'本社、大阪支店-堺井上、堺福田松原'
        },
        {
          url:'/business',
          icon:require('../../assets/images/onlineShop.png'),
          title:'ネットショップ',
          text:'インターネット上で商品 を販売するWEBサイト'
        },
        {
          url:'/warehouse',
          icon:require('../../assets/images/declare.png'),
          title:'船便通関代行サービス',
          text:'輸入業務では'
        },
        {
          url:'/cooperation',
          icon:require('../../assets/images/market.png'),
          title:'市場に提案',
          text:'対し共に市場開拓する'
        },
      ],
      carousels:[
        {
          id:'1',
          url:'/index',
          name:"海外倉庫",
          baseTitle:"標準サービス",
          baseText:"デバンニング　保管　梱包　商品ラベル貼付　出荷",
          optionTitle:"標準サービス",
          optionText:"品質検品　領収書封入　梱包資材指定　撮影・採寸　  配達不能返送対応　購入者様からの返品対応",
        },
        {
          id:'2',
          url:'/business',
          name:"ネットショップ",
          baseTitle:"標準サービス",
          baseText:"デバンニング　保管　梱包　商品ラベル貼付　出荷",
          optionTitle:"標準サービス",
          optionText:"品質検品　領収書封入　梱包資材指定　撮影・採寸　  配達不能返送対応　購入者様からの返品対応",
        },
        {
          id:'3',
          url:'/warehouse',
          name:"船便通関代行サービス",
          baseTitle:"標準サービス",
          baseText:"デバンニング　保管　梱包　商品ラベル貼付　出荷",
          optionTitle:"標準サービス",
          optionText:"品質検品　領収書封入　梱包資材指定　撮影・採寸　  配達不能返送対応　購入者様からの返品対応",
        },
        {
          id:'4',
          url:'/cooperation',
          name:"市場に提案",
          baseTitle:"標準サービス",
          baseText:"デバンニング　保管　梱包　商品ラベル貼付　出荷",
          optionTitle:"標準サービス",
          optionText:"品質検品　領収書封入　梱包資材指定　撮影・採寸　  配達不能返送対応　購入者様からの返品対応",
        },
      ],
      indicator:[
        {
          id:'1',
          name:"海外倉庫",
        },
        {
          id:'2',
          name:"ネットショップ",
        },
        {
          id:'3',
          name:"船便通関代行サービス",
        },
        {
          id:'4',
          name:"市場に提案",
        },
      ],
      maps:[
        {
          mapCenter:{lng: 139.653548, lat: 35.723395},
          title:'堺井上倉庫',
          text:'599-8112 大阪府大阪堺日置荘原寺町471-1',
          telephone:'072-294-6355',
          FAX:'072-294-338'
        },
        {
          mapCenter:{lng: 135.482284, lat: 34.574698},
          title:'堺福田倉庫',
          text:'589-0001 大阪府狭山市東野西3-746',
          telephone:'0722-89-8396',
          FAX:''
        },
        {
          mapCenter:{lng: 135.552178, lat: 34.563345},
          title:'松原倉庫',
          text:'580-0014 大阪府松原市岡7-238',
          telephone:'0722-89-6796',
          FAX:''
        },
        {
          mapCenter:{lng: 135.295576, lat: 34.406605},
          title:'大阪支店',
          text:'589-0001 大阪府狭山市東野西3-746',
          telephone:'0723-49-4939',
          FAX:'0723-49-4941'
        },
      ],
      activeName: 'second'
    };
  },
  methods: {
    arrowClick(val) {
      if(val === 'next') {
        this.$refs.cardShow.next()
      } else {
        this.$refs.cardShow.prev()
      }
    },
    handleIndicat(e){
      console.log(e)
    }
  },
};
</script>

<style lang="scss" scoped>.container {
  background-color: #fff;
  .header {
    position: relative;
    .head {
      background-color: #fff;
      width: 1200px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      font-size: 35px;
      padding: 6px 0 5px 0;
      .left {
        display: flex;
        align-items: center;
  
        img {
          margin-right: 10px;
        }
      }

      .right {
        display: flex;
        align-items: center;
        margin-right: 19px;
        font-family: STYuanti-SC-Light;
        line-height: 22px; 
        color: #828282;
        img {
          width: 36px;
          height: 36px;
          opacity: .3;
          border: solid 1px #969494;
          padding: 8px;
          border-radius: 50%;
          margin-right: 6px;
        }
      }
    }
    .nav {
      background-color: #4b3f89;
      .select {
        width: 1200px;
        margin: 0 auto;
        display: flex;
        line-height: 87px;
        flex-direction: row-reverse;
        color: #fff;
        font-family: SourceHanSansCN-Normal;
        font-size: 16px;
        font-weight: normal;
        letter-spacing: 0px;

        .item {
          padding: 0 18px;
        }
      }
    }
    .banner {
      background-color: #4f3c8e;
      background-image: url(../../assets/images/websitebanner.png);
      background-repeat: no-repeat;
      min-width: 100%;
      min-height: 440px;
      background-size: 100%;
      position: relative;
      .phone {
        width: 335px;
        height: 56px;
        background-color: #ffffff;
        border: solid 4px #d2414c;
        border-left: none;
        position: absolute;
        transform: translateX(-440px);
        left:50%;
        top: 55%;
        display: flex;
        align-items: center;

        img {
          padding: 12px;
          background-color: #d2414c;
        }

        div {
          width: 202px;
          height: 24px;
          margin: auto;
          font-family: SourceHanSansCN-Normal;
          font-size: 30px;
          font-weight: normal;
          font-stretch: normal;
          line-height: 22px;
          letter-spacing: 0px;
          color: #d2414c;
        }
      }
    }
    .service {
      position: absolute;
      bottom: -119px;
      left: 50%;
      transform: translateX(-50%);
      width: 1170px;
      height: 202px;
      margin: auto;
      background-color: #ffffff;
      box-shadow: 0px 20px 73px 0px rgba(0, 0, 0, 0.11);
      display: flex;
      align-items: center;
      box-shadow: 0px 20px 73px 0px 
  rgba(0, 0, 0, 0.11);
      .serve{
        width: 231px;
        height: 204px;
        padding-left: 30px;
        background-color: #ffffff;
        display: flex;
        flex-direction: column;
        justify-content: center;
        .serviceName{
          height: 18px;
          margin-top: 22px;
          font-family: SourceHanSansCN-Medium;
          font-size: 18px;
          font-weight: bolder;
          line-height: 22px;
          letter-spacing: 0px;
          color: #6f6f6f;
          margin-bottom: 8px;
        }
        .serviceText{
          width: 170px;
          height: 35px;
          font-family: SourceHanSansCN-Normal;
          font-size: 15px;
          line-height: 20px;
          color: #c4c4c4;
          word-break:keep-all;
          word-wrap:break-word;
        }
      }
      .serveScope{
        width: 246px;
        height: 204px;
        background-color: #4b3f89;
        display: flex;
        flex-direction: column;
        justify-content: center;
        .title{
          width: 180px;
          margin: auto;
          margin-bottom: 14px;
          font-family: SourceHanSansCN-ExtraLight;
          font-size: 24px;
          font-weight: 100;
          line-height: 22px;
          color: rgba(255, 255, 255, .8);
        }
        .text{
          width: 132px;
          margin: auto;
          margin-top: 0;
          background: #f00;
          font-family: SourceHanSansCN-Bold;
          font-size: 22px;
          font-weight: bolder;
          color: #ffffff;
        }
      }
    }
  }

  .body{
    .total{
      position: relative;
      padding-bottom: 240px;
      .title{
        width: 160px;
        margin: auto;
        text-align: center;
        padding-top: 226px;
        padding-bottom: 28px;
        font-family: SourceHanSansCN-Medium;
        font-size: 39px;
        font-weight: bolder;
        color: #2c2c2c;
      }
      .text{
        width: 730px;
        height: 49px;
        margin: auto;
        text-align: center;
        font-family: SourceHanSansCN-Light;
        font-size: 20px;
        line-height: 29px;
        color: #2c2c2c;
        opacity: 0.8;
      }
      .img{
        width: 1305px;
        margin: auto;
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
      }
    }
    .house{
      background-color: #f0f0f2;
      padding-top: 560px;
      .houseview{
        min-width: 100%;
        height: 967px;
        margin: auto;
        background-color: #4b3f89;
        display: flex;
        .left{
          width: 50%;
          position: relative;
          .content{
            width: 600px;
            position: absolute;
            right: 0;
            .el-carousel__item {
              font-size: 14px;
              padding: 107px;
              font-family: SourceHanSansCN-Regular;
              font-size: 16px;
              color: #ffffff;
            }
            .el-carousel__item h3{
              display: flex;
              .carouselName{
                font-family: SourceHanSansCN-Medium;
                font-size: 39px;
                // line-height: 22px;
                color: #ffffff;
                img{
                  position: unset;
                  margin-left: 20px;
                  opacity: 0.6;
                }
              }
            }
            .el-carousel__item .title{
              padding-top: 96px;
              width: 179px;
              font-size: 20px;
              font-family: SourceHanSansCN;
              font-weight: bold;
              color: #FFFFFF;
              line-height: 39px;
            }
            .el-carousel__item .text{
              padding-top: 10px;
              line-height: 2;
              font-size: 16px;
              font-family: SourceHanSansCN;
              font-weight: 400;
              color: #FFFFFF;
              line-height: 32px;
            }
            .indicator{
              width: 520px;
              position: absolute;
              bottom: 100px;
              left: 50%;
              transform: translateX(-50%);
              display: flex;
              justify-content: space-between;
              z-index: 999;
              .indact{
                color: #ffffff;
                height: 19px;
                font-size: 18px;
                font-family: SourceHanSansCN;
                font-weight: 500;
                color: #CBCBCB;
                line-height: 22px;
              }
              .isactive{
                color: #FFFFFF;
                font-size: 20px;
              }
            }
            .arrow{
              display: flex;
              justify-content: space-between;
              .prev{
                img{
                  left: 50px;
                }
              }
              .next{
                img{
                  right: 50px;
                }
              }
              img{
                position: absolute;
                z-index: 999;
                bottom: 60px;
              }
            }
          }
          img{
            position: absolute;
            right: 260px;
            bottom: 0;
            z-index: 99;
          }
        }
        .right{
          width: 50%;
          background-image: url(../../assets/images/houseview.png);
          background-repeat: no-repeat;
        }
      }
      .housemap{
        padding-top: 84px;
        padding-bottom: 81px;
        .name{
          width: 200px;
          margin: auto;
          font-family: SourceHanSansCN-Medium;
          font-size: 39px;
          font-weight: bolder;
          color: #2c2c2c;
          margin-bottom: 64px;
        }
        .location{
          width: 1166px;
          height: 668px;
          margin: auto;
          display: flex;
          .left{
            margin-right: 14px;
            padding-bottom: 200px;
            background: #fff;
            .icon{
              width: 431px;
              height: 505px;
              .Bmap{
                  width: 100%;
                  height: 100%;
                  ::v-deep.anchorBL{
                    display: none;
                  }
              }
            }
            .title{
              width: 36px;
              padding-bottom: 15px;
              margin-top: 39px;
              margin-left: 19px;
              font-family: SourceHanSansCN-Bold;
              font-size: 18px;
              font-weight: bolder;
              color: #333333;
            }
            .text{
              margin-left: 19px;
              font-family: SourceHanSansCN-Regular;
              font-size: 16px;
              color: #787878;
            }
          }
          .right{
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            .item{
              background: #fff;
              &:nth-child(1){
                margin-bottom: 14px;
              }
              &:nth-child(2){
                margin-bottom: 14px;
              }
              .icon{
                width: 354px;
                height: 205px;
                background-color: #ffffff;
                .Bmap{
                    width: 100%;
                    height: 100%;
                    ::v-deep.anchorBL{
                      display: none;
                    }
                }
              }
              .title{
                margin: 34px 0 10px 10px;
                height: 17px;
                font-family: SourceHanSansCN-Bold;
                font-size: 18px;
                font-weight: bolder;
                line-height: 22px;
                color: #333333;

              }
              .text{
                padding-left: 10px;
                font-family: SourceHanSansCN-Regular;
                font-size: 16px;
                color: #787878;
              }
              div{
                display: flex;
                &:nth-child(4){
                  span{
                    display: block;
                    width: 40px;
                  }
                  .spanF{
                    display: block;
                    width: 40px;
                    margin-left: 10px;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  .footer {
    background: #2c2c2c;

    .foote {
      width: 1404px;
      height: 219px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      align-items: center;

      .title {
        width: 300px;
        display: flex;
        margin-top: 25px;
        padding: 2px 6px 5px 3px;
        justify-content: space-between;
        align-items: center;
        // background: #fff;

        .name {
          font-family: SourceHanSansCN-Medium;
          font-size: 20px;
          font-weight: normal;
          letter-spacing: -1px;
          color: #b8b8b8;
        }
      }

      .linear {
        width: 900px;
        height: 1px;
        opacity: 0.32;
        margin: 32px 0 14px 0;
        background-color: rgb(125, 125, 125, 1);
      }

      .address {
        display: flex;
        flex-direction: column;
        align-items: center;

        .text {
          font-family: SourceHanSansCN-Light;
          font-size: 14px;
          line-height: 25px;
          color: #b8b8b8;
        }
      }

    }
  }
}</style>
