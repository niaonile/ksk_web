<template>
    <div :id="id" :style="{width, height}"></div>
</template>
<script>
export default {
    name: 'Gmap',
    props: {
        id: {
            type: String,
            default: () => {
                return "gMap";
            },
        },
        lng: { 
            type: Number | String,
            default: () => {
                return 36.52732473456851
            }
        },
        lat: {
            type: Number | String,
            default: () => {
                return 138.48109006910846
            }
        },
        width: {
            type: String,
            default: () => {
                return "100%";
            },
        },
        height: {
            type: String,
            default: () => {
                return "400px";
            },
        },
    },
    data() {
        return {
            map: null,
            markers: []
        }
    },
    mounted() {
        this.initMap();
    },
    methods: {
        // 初始化地图
        initMap () {
            this.map = new google.maps.Map(document.getElementById(this.id), {
                // 缩放的数值
                zoom: 16, 
                // 地图中心坐标点
                center: {
                    lat: this.lat,
                    lng: this.lng
                }, 
                // 地图类别
                mapTypeId: google.maps.MapTypeId.ROADMAP 
            });
            const marker = new google.maps.Marker({
                position: {
                    lat: this.lat,
                    lng: this.lng
                },
                map: this.map,
                title: "",
                draggable: true,
            });
            google.maps.event.addListener(marker, 'dragend', (event) => {
                this.mouseM(event);
            })
            this.markers.push(marker);
        },
        // 根据拖拽确定坐标
        mouseM(data) {
            let markPosition = data.latLng.lng() + ',' + data.latLng.lat()
            this.$emit('markChange', markPosition)
        },
    }
}
</script>