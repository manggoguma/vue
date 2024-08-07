<template>
    <div class="sidebar">
        <div class="mainLogo">
            <img class="mainLogoimg" src="@/assets/icons/image 1.svg" alt="" />
        </div>
        <div class="sidebarMenus">
        <div>
            <img src="@/assets/icons/Dashboard_Icon-Black.svg" alt="" />
            <a>Dashboard</a>
        </div>
        <div>
            <img src="@/assets/icons/한시적 주차Icon-Black.svg" alt="" />
            <a>한시적 주차 허용</a>
        </div>
        <div>
            <img src="@/assets/icons/공지사항Icon-Black.svg" alt="" />
            <a>공지사항</a>
        </div>
        <div>
            <img src="@/assets/icons/문의내역Icon-Black.svg" alt="" />
            <a>1:1 문의내역</a>
        </div>
        <div>
            <img src="@/assets/icons/제보Icon-Black.svg" alt="" />
            <a>주차장 제보</a>
        </div>
        <div>
            <img src="@/assets/icons/예약리스트Icon-Black.svg" alt="" />
            <a>예약리스트</a>
        </div>
        <div>
            <img src="@/assets/icons/주차장리스트Icon-Black.svg" alt="" />
            <a>주차장 소유자 관리</a>
        </div>
        <div>
            <img src="@/assets/icons/매출통계Icon-Black.svg" alt="" />
            <a>매출 통계</a>
        </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ShipChajang'
}
</script>

<style>
.sidebar {
    width: 280px;
    /* background-color: blue; */
}
.mainLogo{
    /* background-color: beige; */
    
}
.mainLogoimg{
    margin-right:60px;
    /* background-color: azure; */
}
.sidebarMenus{
    margin-top: 80px;
    margin-left: 50px;
    /* background-color: aqua; */
   
}

.sidebarMenus div{
    margin-left: 20px;
    margin-bottom: 20px;
    text-align: left;
}

.sidebarMenus a{
  padding-left:20px;
  
}
</style>
