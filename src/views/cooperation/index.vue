<template>
    <div class="container">
        <div class="banner">
            <el-image fit="cover" class="image" :src="require('@/assets/images/banner3.png')"></el-image>
            <div class="imgText">
                <el-image fit="none" :src="require('@/assets/images/banner3_text.png')"></el-image>
            </div>
        </div>
        <div class="content">
            <Sidebar />
            <div class="main">
                <div class="link">
                    <router-link to="/index">有限会社ケイ・エス・ケイ</router-link>>
                    <router-link to="/enterprise">トップページ</router-link>>
                    <router-link to>お問合せ</router-link>
                </div>
                <div class="line"></div>
                <div class="linear">
                    <div class="text">企業の理念</div>
                </div>
                <div class="linearText">
                    <div>内外の法およびその精神を遵守し、人材育成、サービス向上。</div>
                    <div>国内･外資企業の国際活動をサポートし，国際的な経済文化交流の発展に努めます。</div>
                </div>
                <div class="point">
                    <div>| 5つのPoint</div>
                </div>
                <div class="line"></div>
                <div class="tips">
                    <div class="tipOne">輸入代行の小さなご要望から製品開発までのフルサポートまで、お客様に合わせた柔軟なカスタマイズ</div>
                    <div class="tipOne">ご要望をワンストップでお引き受けするので、お客様の手間の最小限化を実現</div>
                    <div class="tipTwo">
                        <div>繁忙期、閑散期に対応できる</div>
                        <div>自社システムで発送代行サービスを管理 受注-入庫-マスタ-出荷-在庫オーダー状態一目瞭然</div>
                        <div>お客様と市場のニーズのベストマッチング、さらには新しい市場の発見・開拓をサポートします。</div>
                    </div>
                </div>
                <div class="linear">
                    <div class="text">お問い合わせフォーム</div>
                </div>
                <div class="information">
                    <div>| お客様情報</div>
                </div>
                <div class="form">
                    <el-form :model="ruleForm" :rules="rules" ref="ruleForm" hide-required-asterisk label-width="179px">
                        <el-form-item label="会社名" prop="company">
                            <el-input class="input" v-model="ruleForm.company"></el-input>
                        </el-form-item>
                        <el-form-item prop="name" :show-message="false">
                            <span slot="label">
                                <span>お名前</span>
                                <span style="color: red">【必須】</span>
                            </span>
                            <el-input class="input" v-model="ruleForm.name"></el-input>
                        </el-form-item>
                        <el-form-item label="フリガナ" prop="Katakana">
                            <el-input class="input" v-model="ruleForm.Katakana"></el-input>
                        </el-form-item>
                        <el-form-item label="所在地" prop="Location">
                            <el-input class="input" v-model="ruleForm.Location"></el-input>
                        </el-form-item>
                        <el-form-item label="TEL">
                            <div class="input">
                                <el-col :span="5">
                                    <el-form-item prop="telephone1">
                                       <el-input v-model="ruleForm.telephone1" maxlength="3"></el-input>
                                    </el-form-item>
                                </el-col>
                                <el-col :span="1" style="text-align: center">-</el-col>
                                <el-col :span="5">
                                    <el-form-item prop="telephone2">
                                       <el-input v-model="ruleForm.telephone2" maxlength="4"></el-input>
                                    </el-form-item>
                                </el-col>
                                <el-col :span="1" style="text-align: center">-</el-col>
                                <el-col :span="5">
                                    <el-form-item prop="telephone3">
                                       <el-input v-model="ruleForm.telephone3" maxlength="4"></el-input>
                                    </el-form-item>
                                </el-col>
                            </div>
                        </el-form-item>
                        <el-form-item prop="email" :show-message="false">
                            <span slot="label">
                                <span>E-mail</span>
                                <span style="color: red">【必須】</span>
                            </span>
                            <el-input class="input" v-model="ruleForm.email"></el-input>
                        </el-form-item>
                        <el-form-item prop="consult" :show-message="false">
                            <span slot="label">
                                <span>お問い合わせ内容</span>
                                <span style="color: red;margin-left: -9px;">【必須】</span>
                            </span>
                            <el-input class="input" type="textarea" :rows="3" v-model="ruleForm.consult"></el-input>
                        </el-form-item>
                    </el-form>
                    <div class="btn">
                        <el-button type="primary" @click="submitForm('ruleForm')">提 出</el-button>
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
            ruleForm: {
                name: '',
                email: '',
                consult: '',
                company: '',
                Katakana: '',
                Location: '',
                telephone1: '',
                telephone2: '',
                telephone3: '',
            },
            rules: {
                name: [
                    { required: true, message: '入力してくださいお名前', trigger: 'blur' },
                ],
                email: [
                    { required: true, message: 'please enter the email', trigger: 'blur' },
                    { type: 'email', message: 'please enter the correct email', trigger: ['blur', 'change'] }
                ],
                consult: [
                    { required: true, message: '入力してください内容', trigger: 'blur' },
                ],
            }
        }
    },
    methods: {
        submitForm(formName) {
            this.$refs[formName].validate((valid) => {
                if (valid) {
                    this.$message({
                        message: '提交成功',
                        type: 'success'
                    });
                    this.$refs[formName].resetFields();
                    console.log(this.ruleForm)
                }
            });
        },  
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
                width: 808px;
                margin: 18px 0 16px 0;
                height: 1px;
                border-bottom: solid 1px #dfdfdf;
            }

            .point {
                display: flex;
                align-items: center;
                margin-top: 29px;
                font-size: 18px;
                font-weight: bolder;
                line-height: 25px;
                letter-spacing: 1px;
                color: #6551a8;
            }

            .tips {
                display: flex;
                justify-content: space-between;
                font-family: SourceHanSansCN-Regular;
                font-size: 12px;
                font-weight: bolder;
                line-height: 25px;
                letter-spacing: 1px;
                color: #333333;
                margin-bottom: 27px;

                .tipOne {
                    width: 182px;
                    background-color: rgba(101, 81, 168, 0.2);
                    border-radius: 3px;
                    padding: 18.5px 22px;
                }

                .tipTwo {
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;

                    div {
                        width: 422px;
                        background-color: rgb(101, 81, 168, 0.2);
                        border-radius: 3px;
                        padding-top: 5px;
                        padding-bottom: 5px;

                        &:nth-child(1),
                        &:nth-child(2),
                        &:nth-child(3) {
                            padding-left: 30px;
                            line-height: 2;
                        }

                        &:nth-child(2) {
                            margin: 5px 0;
                        }
                    }
                }
            }

            .information {
                font-size: 14px;
                font-weight: bolder;
                line-height: 25px;
                letter-spacing: 1px;
                color: #6551a8;
                padding-top: 4px;
                padding-bottom: 20px;
            }

            .form {
                .el-form {
                    border: solid 1px #434343;
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    ::v-deep.el-form-item {
                        margin-bottom: 0;
                        border-bottom: 1px solid #434343;
                        &:last-child {
                            border-bottom: none;
                        }
                        .el-form-item__label {
                            color: #000;
                            text-align: left;
                            background: rgba(98, 79, 165, 0.1);
                            border-right: 1px solid #000;
                            padding: 12px 20px 12px 28px;
                        }
                        .el-form-item__content {
                            .input {
                                padding: 9px 10px;
                            }
                            .el-form-item__error {
                                top: unset;
                                left: 10px;
                                bottom: 0;
                            }
                        }
                    }
                }

                .btn {
                    margin: 22px 0 71px 0;
                    display: flex;
                    justify-content: center;

                    .el-button {
                        width: 383px;
                        height: 51px;
                        background-color: #6551a8;
                        border-radius: 26px;
                        font-size: 18px;
                        font-weight: bold;
                        color: #FFFFFF;
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

            .linearText {
                font-size: 14px;
                font-weight: 400;
                color: #666666;
                line-height: 30px;
                text-indent: 3px;
            }
        }
    }
}
</style>