<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  phone: '',
  date: '',
  time: '',
  guests: '',
  occasion: ''
})

const submitted = ref(false)

const submit = () => {
  const { name, phone, date, time, guests } = form.value
  if (!name.trim() || !phone.trim() || !date || !time || !guests) {
    alert('请完整填写姓名、电话、日期、时段和人数。')
    return
  }
  submitted.value = true
  form.value = { name: '', phone: '', date: '', time: '', guests: '', occasion: '' }
  setTimeout(() => {
    submitted.value = false
  }, 6000)
}
</script>

<template>
  <section class="section reserve" id="reserve">
    <div class="container">
      <div class="section-head">
        <p class="section-eyebrow">RESERVATION</p>
        <h2>在线预订</h2>
        <p class="section-intro">提前预约雅座，让我们为您备好一席佳宴。</p>
      </div>
      <div class="reserve-grid">
        <div class="reserve-info">
          <div class="info-item">
            <div class="info-icon">📍</div>
            <div><b>门店地址</b><span>四川省成都市金牛区云锦轩</span></div>
          </div>
          <div class="info-item">
            <div class="info-icon">☎</div>
            <div><b>预订电话</b><span>021-8888 6666</span></div>
          </div>
          <div class="info-item">
            <div class="info-icon">✉</div>
            <div><b>电子邮箱</b><span>reserve@yunjinxuan.example.com</span></div>
          </div>
          <div class="hours">
            <b>午市</b><span>11:00 - 14:30</span>
            <b>晚市</b><span>17:00 - 22:00</span>
            <b>休息日</b><span>每周一闭店（法定节假日除外）</span>
          </div>
        </div>
        <form class="reserve-form" @submit.prevent="submit" novalidate>
          <h3>填写预订信息</h3>
          <div class="form-row">
            <div class="field">
              <label for="name">您的姓名</label>
              <input id="name" name="name" type="text" placeholder="请输入姓名" v-model="form.name" />
            </div>
            <div class="field">
              <label for="phone">联系电话</label>
              <input id="phone" name="phone" type="tel" placeholder="手机号码" v-model="form.phone" />
            </div>
          </div>
          <div class="form-row">
            <div class="field">
              <label for="date">用餐日期</label>
              <input id="date" name="date" type="date" v-model="form.date" />
            </div>
            <div class="field">
              <label for="time">用餐时段</label>
              <select id="time" name="time" v-model="form.time">
                <option value="">请选择时段</option>
                <option>午市 11:00 - 14:30</option>
                <option>晚市 17:00 - 22:00</option>
              </select>
            </div>
          </div>
          <div class="form-row">
            <div class="field">
              <label for="guests">用餐人数</label>
              <select id="guests" name="guests" v-model="form.guests">
                <option value="">请选择人数</option>
                <option>1 - 2 人</option>
                <option>3 - 4 人</option>
                <option>5 - 8 人</option>
                <option>8 人以上（包厢）</option>
              </select>
            </div>
            <div class="field">
              <label for="occasion">用餐场合</label>
              <select id="occasion" name="occasion" v-model="form.occasion">
                <option value="">可选</option>
                <option>家庭聚餐</option>
                <option>朋友小聚</option>
                <option>商务宴请</option>
                <option>纪念日</option>
              </select>
            </div>
          </div>
          <div class="form-actions">
            <button type="submit" class="btn-submit">提交预订</button>
          </div>
          <p class="form-note">提交后将有专人致电确认，请保持电话畅通。</p>
          <div v-if="submitted" class="form-ok" style="display: block">
            ✓ 预订信息已提交，我们将在 30 分钟内与您确认。
          </div>
        </form>
      </div>
    </div>
  </section>
</template>
