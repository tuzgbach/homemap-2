<template>
  <div id="FooterMain" class="w-full bg-[#E8E8E8] mt-10">
    <div class="max-w-[1200px] mx-auto py-4 px-4">
      <div class="md:flex gap-8 justify-between w-full">
        <!-- Phần 1 -->
        <div class="md:w-[50%]">
          <div class="title">Trợ giúp</div>
          <div class="content">
            Trung tâm Trợ giúp, Tranh chấp & Báo cáo, Bảo vệ Người mua, Báo cáo
            Vi phạm Quyền sở hữu Trí tuệ, Trung tâm Trợ giúp Thông tin Quy định,
            Tranh chấp & Báo cáo, Bảo vệ Người mua, Báo cáo Vi phạm Quyền sở hữu
            Trí tuệ, Trung tâm Trợ giúp Thông tin Quy định
          </div>
        </div>

        <!-- Phần 2 -->
        <div class="md:w-[50%]">
          <div class="title">Các trang AliExpress đa ngôn ngữ</div>
          <div class="content">
            Nga, Bồ Đào Nha, Tây Ban Nha, Pháp, Đức, Ý, Hà Lan, Thổ Nhĩ Kỳ, Nhật
            Bản, Hàn Quốc, Thái Lan, Tiếng Việt, Ả Rập, Hebrew, Ba Lan
          </div>
        </div>
      </div>

      <div class="md:flex gap-8 justify-between w-full mt-8">
        <!-- Phần 3 -->
        <div class="md:w-[50%]">
          <div class="title">Duyệt theo danh mục</div>
          <div class="content">
            Tất cả phổ biến, Sản phẩm, Khuyến mãi, Giá thấp, Giá trị tốt, Đánh
            giá, Blog, Cổng người bán, BLACK FRIDAY, Trợ lý AliExpress
          </div>
        </div>

        <!-- Phần 4 -->
        <div class="md:w-[50%]">
          <div class="title">Nhóm Alibaba</div>
          <div class="content">
            Trang web Nhóm Alibaba, AliExpress, Alimama, Alipay, Fliggy, Alibaba
            Cloud, Alibaba International, AliTelecom, DingTalk, Juhuasuan,
            Taobao Marketplace, Tmall, Taobao Global, AliOS, 1688
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Phần FooterSub -->
  <div id="FooterSub" class="w-full bg-[#333333] text-sm text-gray-400">
    <div class="max-w-[1200px] mx-auto py-4 px-4">
      <div class="flex flex-col md:flex-row items-center justify-between">
        <div class="text-center md:text-left">
          Bảo vệ Quyền Sở hữu Trí tuệ - Chính sách Bảo mật - Bản đồ trang web - Điều
          khoản Sử dụng - Thông tin cho người tiêu dùng ở Liên minh châu Âu - Thỏa
          thuận Dịch vụ Giao dịch cho người tiêu dùng không thuộc Liên minh châu
          Âu/Hoa Kỳ - Điều khoản và Điều kiện cho người tiêu dùng ở Liên minh châu
          Âu/Khu vực Kinh tế chung/Hoa Kỳ (Giao dịch) - Hướng dẫn pháp lý về thông
          tin người dùng ©️2010-2022 AliExpress.com. Bảo lưu mọi quyền. Giấy phép
          kinh doanh dịch vụ viễn thông giá trị gia tăng
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Chỉnh sửa phần FooterMain */
#FooterMain {
  background-color: #ffffff;
  color: #333333;
}

#FooterMain .title {
  font-size: 12px;
  font-weight: bold;
  color: #555555;
  margin-bottom: 4px;
}

#FooterMain .content {
  font-size: 14px;
  color: #777777;
  line-height: 1.5;
}

/* Chỉnh sửa phần FooterSub */
#FooterSub {
  background-color: #fdebd2;
  color: #2d2d2d;
  text-align: center;
}

#FooterSub a {
  color: #2d2d2d;
  text-decoration: underline;
}

/* Trung tâm footer trên màn hình lớn */
@media (min-width: 768px) {
  #FooterMain,
  #FooterSub {
    display: flex;
    justify-content: center;
  }
}

/* Style the copyright text */
#Copyright {
  font-size: 10px;
  margin-top: 4px;
}
</style>

<script setup></script>
