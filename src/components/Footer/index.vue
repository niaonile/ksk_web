<template>
    <div class="footer">
        <div class="title">
            <img src="../../assets/images/iconLogo.png" alt="">
            <div class="name">有限会社   ケイ・エス・ケイ</div>
        </div>
        <div class="linear"></div>
        <div class="info">
            <div class="text">有限会社ケイ・エス・ケイ</div>
            <div class="text">〒178-0063 東京都練馬区東大泉5-21-10</div>
            <div class="text">
                <span>TEL：03-6323-5070</span>
                <span>FAX：03-6323-5070</span>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.footer {
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #e7e7e7;
    .title {
        width: 300px;
        padding: 25px 0 21px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        .name {
            font-size: 20px;
            font-weight: bold;
            color: #333333;
        }
    }
    .linear{
        width: 1200px;
        height: 1px;
        background: linear-gradient(to right, #e7e7e7, rgba(125, 125, 125, .32), #e7e7e7);
    } 
    .info {
        text-align: center;
        padding: 14px 0 31px;
        .text {
            line-height: 25px;
            font-size: 14px;
            color: #666666;
            font-family: SourceHanSansCN-Light;
            span {
                padding: 0 5px;
            }
        }
    }
}
</style>