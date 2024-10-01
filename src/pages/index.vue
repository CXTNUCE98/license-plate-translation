<script lang="ts" setup>
console.log('11242');
const input = ref('')
</script>

<template>
    <div class="section bg-fill bg-main relative flex justify-center">
        <div class="w-86% text-white max-w-1270px">
            <div class="pb-30px">
                <h1 class="text-35px mb-14px">
                    Dịch biển số xe Online – Phần mềm xem ý nghĩa biển số xe máy, ô tô
                </h1>

                <div class="text-17px">
                    Dịch biển số xe có nghĩa giải mã bí ẩn các con số theo phong thủy để đưa ra cái nhìn đa chiều về chúng,
                    từ đó biết được biển số xe đó là tốt hay xấu? Tương sinh hay tương khắc với bản mệnh? Với
                    dichbiensoxe.com, chỉ mất vài giây bạn sẽ có được bản luận giải hoàn chỉnh ý nghĩa biển số xe của mình,
                    hãy cùng khám phá!
                </div>
            </div>

            <div class="flex gap-6 flex justify-center">
                <!-- <div> -->
                <div class="flex-1 w-605px text-black bg-white rounded-lg px-10px py-15px">
                    <h2 class="text-21px font-bold pl-10px">Dịch Biển Số Xe Online</h2>
                    <div class="px-10px mb-20px">
                        <span class="font-bold cursor-pointer">Dichbiensoxe.com</span> phần mềm dịch biển số xe online chính
                        xác và chi tiết nhất hiện nay. Phần mềm Dịch Biển Số Xe hoàn toàn miễn phí và giải đáp cho các bạn ý
                        nghĩa phong thủy ẩn đằng sau bên trong biển số xe.
                    </div>

                    <div class="rounded-lg bg-#EDEDED py-10px px-25px">
                        <div class="font-bold">NHẬP BIỂN SỐ XE CỦA BẠN</div>

                        <div class="flex items-center gap-1">
                            <div class="bg-white rounded-50px px-15px py-10px flex items-center">
                                <input class="outline-none h-29px" style="width: 386px" v-model="input" placeholder="Nhập 5 số biển số xe"/>
                            </div>
                            <button  class="w-123px h-50px bg-#AD0909 rounded-50px flex items-center justify-center text-white"><i class='bx bx-search text-20px'></i></button>
                        </div>
                    </div>
                </div>
                <div class="flex-1 w-605px">2</div>
                <!-- </div> -->
            </div>
        </div>
    </div>
</template>

<style scoped>
.honey-img {
    height: 690px;
    width: 474px;
    overflow: hidden;
}

.vertical-text {
    writing-mode: vertical-rl;
    text-orientation: mixed;
    transform: rotate(180deg);
    white-space: nowrap;
    font-family: Arial, sans-serif;
    font-size: 51px;
    color: #E6E6E6;
    font-weight: bold;
}

.section {
    padding-top: 50px;
    padding-bottom: 50px;
    background-color: rgb(173, 9, 9);
}

.bg-main {
    background-image: url(../public/bg_main.png);
    background-position: 77% 41%;
}

.bg-fill {
    background-size: cover !important;
    background-repeat: no-repeat !important;
    background-position: 50% 50%;
}


</style>