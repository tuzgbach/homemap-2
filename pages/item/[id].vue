<template>
  <MainLayout>
    <div id="ItemPage" class="mt-4 max-w-[1200px] mx-auto px-2">
      <div class="md:flex gap-4 justify-between mx-auto w-full">
        <div class="md:w-[40%]">
          <img
            v-if="currentImage"
            class="rounded-lg object-fit"
            :src="currentImage" />
          <div
            v-if="images[0] !== ''"
            class="flex items-center justify-center mt-2">
            <div v-for="image in images">
              <img
                @mouseover="currentImage = image"
                @click="currentImage = image"
                width="70"
                class="rounded-md object-fit border-[3px] cursor-pointer"
                :class="currentImage === image ? 'border-[#FF5353]' : ''"
                :src="image" />
            </div>
          </div>
        </div>
        <div class="md:w-[60%] bg-white p-3 rounded-lg">
          <div v-if="product && product.data">
            <p class="mb-2">{{ product.data.title }}</p>
            <p class="font-light text-[12px] mb-2">
              {{ product.data.description }}
            </p>
          </div>

          <div class="flex items-center pt-1.5">
            <span class="h-4 min-w-4 rounded-full p-0.5 bg-[#FFD000] mr-2">
              <Icon
                name="material-symbols:star-rounded"
                class="-mt-[17px]"
                size="12" />
            </span>
            <p class="text-[#FF5353]">Giảm thêm 5%</p>
          </div>

          <div class="flex items-center justify-start my-2">
            <Icon name="ic:baseline-star" color="#FF5353" />
            <Icon name="ic:baseline-star" color="#FF5353" />
            <Icon name="ic:baseline-star" color="#FF5353" />
            <Icon name="ic:baseline-star" color="#FF5353" />
            <Icon name="ic:baseline-star" color="#FF5353" />
            <span class="text-[13px] font-light ml-2"
              >5213 Đã xem & 1,000+ sử dụng</span
            >
          </div>

          <div class="border-b" />

          <div class="flex items-center justify-start gap-2 my-2">
            <div class="text-xl font-bold">$ {{ priceComputed }}</div>
            <span
              class="bg-[#F5F5F5] border text-[#C08562] text-[9px] font-semibold px-1.5 rounded-sm"
              >70% off</span
            >
          </div>

          <p class="text-[#009A66] text-xs font-semibold pt-1">
            Miễn phí giao hàng với đơn hàng từ 500,000đ
          </p>

          <p class="text-[#009A66] text-xs font-semibold pt-1">
            Giao hàng 2h nội thành
          </p>

          <div class="py-2" />

          <button
            @click="addToCart()"
            :disabled="isInCart"
            class="custom-button">
            <div v-if="isInCart">Đã thêm vào giỏ</div>
            <div v-else>Thêm vào giỏ hàng</div>
          </button>
        </div>
      </div>
    </div>
  </MainLayout>
</template>

<script setup>
import MainLayout from "~/layouts/MainLayout.vue";
import { useUserStore } from "~/stores/user";
const userStore = useUserStore();

const route = useRoute();

let product = ref(null);
let currentImage = ref(null);

onBeforeMount(async () => {
  product.value = await useFetch(
    `/api/prisma/get-product-by-id/${route.params.id}`
  );
});

watchEffect(() => {
  if (product.value && product.value.data) {
    currentImage.value = product.value.data.url;
    images.value[0] = product.value.data.url;
    userStore.isLoading = false;
  }
});

const isInCart = computed(() => {
  let res = false;
  userStore.cart.forEach((prod) => {
    if (route.params.id == prod.id) {
      res = true;
    }
  });
  return res;
});

const priceComputed = computed(() => {
  if (product.value && product.value.data) {
    return product.value.data.price / 100;
  }
  return "0.00";
});

const images = ref([
  "",
  "https://picsum.photos/id/212/800/800",
  "https://picsum.photos/id/233/800/800",
  "https://picsum.photos/id/165/800/800",
  "https://picsum.photos/id/99/800/800",
  "https://picsum.photos/id/144/800/800",
]);

const addToCart = () => {
  userStore.cart.push(product.value.data);
};
</script>
<style scoped>
.custom-button {
  /* Các thuộc tính mặc định cho button */
  padding: 10px 20px;
  border: none;
  border-radius: 8px;
  font-size: 16px;
  font-weight: bold;
  color: white;
  background: linear-gradient(to right, #fe0130, #fe0131);
  transition: background 0.3s ease-in-out; /* Hiệu ứng chuyển đổi màu nền */

  /* Hiệu ứng hover */
  cursor: pointer;
}

.custom-button:hover {
  background: linear-gradient(
    to right,
    #ff2c2c,
    #ff1a1a
  ); /* Màu nền thay đổi khi hover */
}
</style>
