<script setup lang="ts">

// import Travel from "@/public/travel.png"
const Travel = ref()
const email = ref()
</script>

<template>
    <div class="footer-bg flex justify-center items-center ">
        <div class="w-65% flex justify-between flex-wrap">
            <div>
                <img :src="Travel" class="h-64px" alt="travel_logo">
                <p class="text-#757095 max-w-213px py-4">Travel helps companies manage payments easily.</p>

                <div class="flex gap-2 ">
                    <i class='bx bxl-linkedin text-30px text-#DF6951'></i>
                    <i class='bx bxl-messenger text-30px text-#DF6951'></i>
                    <i class='bx bxl-twitter text-30px text-#DF6951'></i>
                    <i class='bx bx-infinite text-30px text-#DF6951'></i>
                </div>
            </div>
            <div>
                <div class="font-bold text-21px text-#181433 pb-2">Company</div>
                <div class="flex flex-col gap-16px font-semibold">
                    <p>About Us</p>
                    <p>Careers</p>
                    <p>Blog</p>
                    <p>Pricing</p>
                </div>
            </div>
            <div>
                <div class="font-bold text-21px text-#181433 pb-2">Destinations</div>
                <div class="flex flex-col gap-16px font-semibold">
                    <p>Maldives</p>
                    <p>Los Angelas</p>
                    <p>Las Vegas</p>
                    <p>Torronto</p>
                </div>
            </div>
            <div>
                <div class="font-bold text-21px text-#181433 pb-2">Join Our Newsletter</div>

                <div class="flex bg-#EEEEFF">
                    <el-input v-model="email"
                        class="[&_.el-input\_\_wrapper]:(outline-none bg-#EEEEFF border-none shadow-none h-52px) [&_.el-input-group\_\_append]:(bg-#DF6951 font-semibold text-white rounded-lg cursor-pointer)"
                        placeholder="Your email address">
                        <template #append class="bg-#DF6951">
                            <div>
                                Subcribe
                            </div>
                        </template>
                    </el-input>

                </div>
                <p class="pt-4 max-w-330px text-#181433">* Will send you weekly updates for your better
                    tour packages.</p>
            </div>
        </div>
        <div class="pt-10">
            Copyright @ Xpro 2022. All Rights Reserved.
        </div>
    </div>
</template>
<style scoped>
.footer-bg {
    background-image: url(../public/footer.png);
    height: 464px;
    width: auto;
}
</style>