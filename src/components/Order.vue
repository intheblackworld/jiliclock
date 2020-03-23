<template>
  <div class="order-bg">
    <!-- <img src="@/projects/fs/order/bg.png" alt="" class="bg-img"> -->
    <!-- <img src="@/projects/fs/order/bg1.png" alt="" class="bg-img no-mix"> -->
    <!-- <img src="@/projects/fs/order/bg_m.jpg" alt="" class="bg-img" v-if="isMobile"> -->
    <div class="order-top">
      <!-- <div class="title-block">
        <h3 class="title">{{order.title}}</h3>
        <div class="subtitle">{{order.subTitle}}</div>
      </div> -->
      <div
        class="order-title"
        v-html="order.title"
      ></div>
      <div
        class="order-subtitle"
        v-html="order.subTitle"
      ></div>
      <div class="order">
        <div class="form">
          <div class="group">
            <div class="row">
              <label>姓名</label>
              <el-input
                v-model="form.name"
                placeholder
              ></el-input>
            </div>
            <div class="row">
              <label>手機</label>
              <el-input
                v-model="form.phone"
                placeholder
              ></el-input>
            </div>
            <div class="row">
              <label>聯絡時間(起)</label>
              <el-time-select
                v-model="form.time_start"
                :editable="false"
                :picker-options="{
                  start: '08:00',
                  step: '01:00',
                  end: '22:00',
                }"
              ></el-time-select>
            </div>
            <div class="row">
              <label>聯絡時間(迄)</label>
              <el-time-select
                v-model="form.time_end"
                :editable="false"
                :picker-options="{
                  start: '08:00',
                  step: '01:00',
                  end: '22:00',
                }"
              ></el-time-select>
            </div>
            <!-- <div class="row">
              <label>想看房型</label>
              <el-select v-model="form.house" placeholder>
                <el-option
                  v-for="city in ['甜蜜2房', '幸福3房', '都想看看']"
                  :key="city"
                  :label="city"
                  :value="city"
                  no-data-text=""
                ></el-option>
              </el-select>
            </div> -->
            <!-- <div class="row">
              <label>E-mail</label>
              <el-input v-model="form.email" placeholder></el-input>
            </div> -->
            <!-- <div class="row">
              <label>居住城市</label>
              <el-select v-model="form.city" placeholder>
                <el-option
                  v-for="city in cityList"
                  :key="city.value"
                  :label="city.label"
                  :value="city.value"
                  no-data-text="無數據"
                ></el-option>
              </el-select>
            </div>
            <div class="row">
              <label>居住地區</label>
              <el-select v-model="form.area" placeholder>
                <el-option
                  v-for="area in areaList"
                  :key="area.value"
                  :label="area.label"
                  :value="area.value"
                  no-data-text="請先選擇居住城市"
                ></el-option>
              </el-select>
            </div> -->
          </div>
          <div class="group">
            <div class="row">
              <el-input
                type="textarea"
                :rows="2"
                placeholder="請輸入您的留言 (選填)"
                v-model="form.msg"
              ></el-input>
            </div>
          </div>
        </div>
        <div class="control">
          <el-checkbox v-model="checked">
            <p>
              本人知悉並同意
              <span @click="showPolicyDialog">「個資告知事項聲明」</span>
              內容
            </p>
          </el-checkbox>
        </div>
        <div class="hint">
          注意事項：<br />
          1.本網站所載之相關事項通知。<br />
          2.客戶管理與服務。<br />
          3. 本公司行銷業務之推廣。<br />
          4. 即刻預約至109.5.30截止，需填寫完整個人資料，並至接待中心完成參觀，即可獲得抽獎券一張。<br />
          5. 獎品分別為蘋果i Phone 11 128G（不選色）乙台、任天堂SWITCH（不選色）乙台、蘋果Air Pods Pro乙台，中獎者需出示身分證供接待中心檢核，並依法繳扣所需稅金後始領取獎品。<br />
          6. 抽獎活動時間為109.7.5（日）、109.8.2（日）、109.9.6（日），每月各抽出一個獎項，本接待中心保有獎項優先順序抽出的權利。會以直播錄影方式播出，中獎者本人需於五日內憑身分證、抽獎券至接待中心領取逾期不候。<br />
          7. 抽獎時間本接待中心保有調整或延後之權利。<br />
          8. 本公司保有活動取消、終止或修改本活動相關內容之權利，如有未盡事宜，悉應本接待中心相關規定或解釋辦理。
        </div>
        <div
          style="margin: 0 auto;z-index:2;"
          v-if="!isMobile"
        >
          <vue-recaptcha
            :sitekey="info.recaptcha_site_key_v2"
            @verify="isVerify = true"
            :loadRecaptchaScript="true"
          ></vue-recaptcha>
        </div>
        <div
          style="margin: 0 auto;z-index:2;"
          v-if="isMobile"
        >
          <vue-recaptcha
            :sitekey="info.recaptcha_site_key_v2"
            @verify="isVerify = true"
            :loadRecaptchaScript="true"
          ></vue-recaptcha>
        </div>
        <el-button
          class="form-submit"
          type="primary"
          :disabled="!checked || !isVerify"
          @click="submit"
          :loading="isSubmit"
        >立即預約</el-button>
        <Loading
          :loading="isSubmit"
          :isOpacity="true"
        />
      </div>
    </div>
    <ContactInfo />
    <GoogleMap />
    <PolicyDialog :policyVisible="policyVisible" />
  </div>
</template>

<script>
import ContactInfo from '@/components/ContactInfo.vue'
import GoogleMap from '@/components/GoogleMap.vue'
import PolicyDialog from '@/components/PolicyDialog.vue'
import info from '@/info'
import { cityList, renderAreaList } from '@/info/address'
import { isMobile } from '@/utils'
import Loading from '@/components/Loading.vue'
import VueRecaptcha from 'vue-recaptcha'

export default {
  name: 'order',
  components: {
    ContactInfo,
    GoogleMap,
    PolicyDialog,
    Loading,
    VueRecaptcha,
  },

  data() {
    return {
      cityList,
      info,
      order: info.order,
      isMobile,
      form: {
        name: '',
        phone: '',
        email: '',
        city: '',
        area: '',
        msg: '',
        time_start: '',
        time_end: '',
      },
      checked: false,
      isSubmit: false,
      isVerify: false, // google 機器人驗證
      policyVisible: false,
      showValidateDialog: false,
    }
  },

  computed: {
    areaList() {
      return renderAreaList(this.form.city)
    },
  },

  methods: {
    showPolicyDialog() {
      this.policyVisible = true
    },

    alertValidate() {
      const h = this.$createElement
      this.$notify({
        title: '請填寫必填欄位',
        message: h(
          'i',
          { style: 'color: #82191d' },
          '「姓名、手機、 聯絡時間」是必填欄位',
        ),
      })
    },

    submit() {
      if (this.isSubmit) return
      if (!this.isVerify) return
      if (!this.checked) return
      this.isSubmit = true
      if (
        !this.form.name ||
        !this.form.phone ||
        !this.form.time_start ||
        !this.form.time_end
        // ||
        // !this.form.email ||
        // !this.form.city ||
        // !this.form.area
      ) {
        this.alertValidate()
        this.isSubmit = false
        return
      }
      const urlParams = new URLSearchParams(window.location.search)
      const utmSource = urlParams.get('utm_source')
      const utmMedium = urlParams.get('utm_medium')
      const utmContent = urlParams.get('utm_content')
      const utmCampaign = urlParams.get('utm_campaign')
      const formData = new FormData()
      formData.append('name', this.form.name)
      formData.append('phone', this.form.phone)
      formData.append('email', this.form.email)
      formData.append('msg', this.form.msg)
      // formData.append('time_start', this.form.time_start)
      // formData.append('time_end', this.form.time_end)
      formData.append('city', this.form.city)
      formData.append('area', this.form.area)
      formData.append('utm_source', utmSource)
      formData.append('utm_medium', utmMedium)
      formData.append('utm_content', utmContent)
      formData.append('utm_campaign', utmCampaign)
      const time = new Date()
      const year = time.getFullYear()
      const month = time.getMonth() + 1
      const day = time.getDate()
      const hour = time.getHours()
      const min = time.getMinutes()
      const sec = time.getSeconds()
      const date = `${year}-${month}-${day} ${hour}:${min}:${sec}`
      fetch(
        `https://script.google.com/macros/s/AKfycbyQKCOhxPqCrLXWdxsAaAH06Zwz_p6mZ5swK80USQ/exec?name=${this.form.name}&phone=${this.form.phone}&email=${this.form.email}&cityarea=${this.form.city}${this.form.area}&msg=${this.form.msg}&utm_source=${utmSource}&utm_medium=${utmMedium}&utm_content=${utmContent}&utm_campaign=${utmCampaign}&date=${date}&campaign_name=${info.caseName}
      `,
        {
          method: 'GET',
        },
      )
      fetch('contact-form.php', {
        method: 'POST',
        body: formData,
      }).then(response => {
        this.isSubmit = false
        if (response.status === 200) {
          window.location.href = 'formThanks'
        }
      })
    },
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/style/variableColor.scss';
.bg-img {
  width: 100vw;
  position: absolute;
  top: 0;
  left: 0;
  height: auto;
  display: block;
  object-fit: cover;
  // mix-blend-mode: screen;
  //background: ("~@/projects/fs/order/bg_m.jpg");
  &.no-mix {
    mix-blend-mode: normal;
    height: 100%;
  }
}
.order-bg {
  background-color: $order_bg_color;
  background-image: $order_bg_image;
  background-repeat: no-repeat;
  position: relative;
  padding-top: 130px;
  background-size: 100vw auto;
  background-attachment: fixed;
  background-position: 0% 50%;
  transform: translateY(0);
  .order-top {
    position: relative;
    overflow: hidden;
  }
  .order-title {
    width: 100vw;
    background-color: #112d81;
    padding-top: 20px;
    padding-bottom: 8px;
    font-weight: bold;
    line-height: 1.3;
    font-size: calc(100vw * 36 / 1920);
    text-align: center;
    color: $order_title_color;
  }

  .order-subtitle {
    width: 100vw;
    background-color: #112d81;
    font-size: 20px;
    text-align: center;
    color: $order_subtitle_color;
    margin-bottom: 40px;
    padding-bottom: 18px;
  }

  .order {
    width: 920px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    margin-bottom: 3rem;
  }

  .form {
    display: flex;
    align-items: flex-start;
    > .group {
      flex: 1;
      align-items: flex-start;
    }
  }

  .group {
    height: 250px;
    margin-bottom: 40px;

    &:nth-child(1) {
      border-right: 1px solid rgba(0, 0, 0, 0.2);
      .row {
        justify-content: flex-start;
      }
    }

    &:nth-child(2) {
      .row {
        justify-content: flex-end;
        align-items: flex-start;
        height: 100%;
      }
    }
  }

  .row {
    display: flex;
    align-items: center;
    margin-bottom: 15px;

    &.house {
      margin-top: 50px;
    }

    &:nth-last-child(1) {
      margin-bottom: 0;
    }

    label {
      width: 92px;
      font-size: 16px;
      opacity: 0.8;
      color: $order_input_label_color;
    }
  }

  .control {
    margin-top: 0px;
    margin-bottom: 20px;
  }

  .hint {
    width: 920px;
    margin: 20px auto;
    padding: 15px;
    font-size: 12px;
    font-weight: 500;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.6;
    letter-spacing: normal;
    text-align: left;
    color: #ffffff;
    background: #112d81;
  }
}

/* 平板尺寸 */
@media only screen and (min-device-width: 768px) and (max-device-width: 1024px) {
  .order-title {
    font-size: 32px;
  }

  .order-subtitle {
    font-size: 16px;
  }

  .order {
    width: 920px;
    margin: 0 auto;
  }
}

/* 螢幕尺寸標準 */
/* 手機尺寸 */
@media only screen and (max-width: 767px) {
  .order-bg {
    background-image: $order_bg_image_m;
    padding-top: 40px;
    margin: 0;
    position: relative;
    z-index: 2;

    > img {
      display: block;
    }
    .order-title {
      padding-top: 10px;
      padding-bottom: 5px;
      font-size: calc(100vw * 38 / 375);
    }

    .order-subtitle {
      // display: none;
      font-size: 21px;
    }
    .order {
      width: 95% !important;
      margin: 0 auto;
      padding: 0;
    }

    .form {
      flex-direction: column;
    }

    .group {
      width: 100%;
      height: auto !important;
      margin-bottom: 0px !important;
      border: none !important;
    }

    .row {
      margin-bottom: 12px !important;

      &.house {
        margin-top: 20px;
      }
      label {
        width: 30% !important;
      }
    }

    .control {
      margin-top: 10px;
      margin-bottom: 10px;
    }

    .hint {
      width: calc(100vw * 334 / 375);
      font-size: 12px;
      font-weight: normal;
      font-stretch: normal;
      font-style: normal;
      line-height: 1.2;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
    }
  }
}
</style>
