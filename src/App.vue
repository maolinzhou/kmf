<template>
  <div class="dashboard">
    <!-- 星星装饰 -->
    <div class="stars">
      <span class="star">★</span>
      <span class="star">★</span>
      <span class="star">★</span>
      <span class="star">★</span>
      <span class="star">★</span>
      <span class="star">★</span>
      <span class="star">★</span>
      <span class="star">★</span>
      <span class="star">★</span>
      <span class="star">★</span>
    </div>

    <!-- 标题 -->
    <div class="header">
      <h1 class="header-title">校园党建可视化大屏</h1>
    </div>

    <!-- 内容区域 -->
    <div class="content">
      <!-- 组织架构 -->
      <div class="card">
        <div class="card-title">组织架构</div>
        <div class="org-structure">
          <div class="org-level">
            <div class="org-item">书记</div>
          </div>
          <div class="org-level">
            <div class="org-item">副书记</div>
          </div>
          <div class="org-level">
            <div class="org-item">组织委员</div>
            <div class="org-item">宣传委员</div>
            <div class="org-item">纪律委员</div>
          </div>
          <div class="org-level">
            <div class="org-item">第一组</div>
            <div class="org-item">第二组</div>
          </div>
          <div class="org-level">
            <div class="org-item">综合办</div>
          </div>
        </div>
      </div>

      <!-- 党费收缴管理 -->
      <div class="card">
        <div class="card-title">党费收缴管理</div>
        <div class="chart-container">
          <v-chart :option="feeChartOption" style="height: 100%;" />
        </div>
      </div>

      <!-- 组织生活会及民主评议党员 -->
      <div class="card">
        <div class="card-title">组织生活会及民主评议党员</div>
        <div class="chart-container">
          <v-chart :option="evaluationChartOption" style="height: 100%;" />
        </div>
      </div>

      <!-- 谈心谈话情况 -->
      <div class="card">
        <div class="card-title">谈心谈话情况</div>
        <div class="progress-bars">
          <div class="progress-item">
            <div class="progress-label">
              <span>新发展党员</span>
            </div>
            <div class="progress-bar">
              <div class="progress-fill" :style="{ width: '85%' }"></div>
            </div>
          </div>
          <div class="progress-item">
            <div class="progress-label">
              <span>流动党员</span>
            </div>
            <div class="progress-bar">
              <div class="progress-fill" :style="{ width: '70%' }"></div>
            </div>
          </div>
          <div class="progress-item">
            <div class="progress-label">
              <span>困难党员</span>
            </div>
            <div class="progress-bar">
              <div class="progress-fill" :style="{ width: '60%' }"></div>
            </div>
          </div>
          <div class="progress-item">
            <div class="progress-label">
              <span>党外分子</span>
            </div>
            <div class="progress-bar">
              <div class="progress-fill" :style="{ width: '45%' }"></div>
            </div>
          </div>
          <div class="progress-item">
            <div class="progress-label">
              <span>关键群体</span>
            </div>
            <div class="progress-bar">
              <div class="progress-fill" :style="{ width: '30%' }"></div>
            </div>
          </div>
        </div>
      </div>

      <!-- 主题党日开展情况 -->
      <div class="card">
        <div class="card-title">主题党日开展情况</div>
        <div class="chart-container">
          <v-chart :option="partyDayChartOption" style="height: 100%;" />
        </div>
      </div>

      <!-- 理论学习情况 -->
      <div class="card">
        <div class="card-title">理论学习情况</div>
        <div style="color: #FFD700; text-align: center; margin-bottom: 20px;">
          <div style="font-size: 36px; font-weight: bold; margin-bottom: 10px;">134</div>
          <div style="font-size: 16px;">本年度集中学习</div>
          <div style="font-size: 14px; margin-top: 5px;">次</div>
        </div>
        <div class="chart-container" style="height: 60%;">
          <v-chart :option="studyChartOption" style="height: 100%;" />
        </div>
      </div>

      <!-- 三会一课 -->
      <div class="card">
        <div class="card-title">三会一课</div>
        <div class="activity-list">
          <div class="activity-item">
            <span class="activity-number">1</span>
            中国共产党为中华民族谋复兴立了7个大历史功劳
          </div>
          <div class="activity-item">
            <span class="activity-number">2</span>
            中国共产党为中华民族谋复兴立了7个大历史功劳
          </div>
          <div class="activity-item">
            <span class="activity-number">3</span>
            中国共产党为中华民族谋复兴立了7个大历史功劳
          </div>
        </div>
      </div>

      <!-- 组织生活 -->
      <div class="card">
        <div class="card-title">组织生活</div>
        <div class="chart-container">
          <v-chart :option="orgLifeChartOption" style="height: 100%;" />
        </div>
      </div>

      <!-- 主题教育/学习教育进展 -->
      <div class="card">
        <div class="card-title">主题教育/学习教育进展</div>
        <div class="education-table">
          <div class="table-header">
            <div>排名</div>
            <div>教育主题</div>
            <div>完成学习次数</div>
          </div>
          <div class="table-row">
            <div>1</div>
            <div>中国共产党简史</div>
            <div>1086</div>
          </div>
          <div class="table-row">
            <div>2</div>
            <div>论中国共产党历史</div>
            <div>936</div>
          </div>
          <div class="table-row">
            <div>3</div>
            <div>习近平新时代中国特色社会主义思想</div>
            <div>813</div>
          </div>
          <div class="table-row">
            <div>4</div>
            <div>毛泽东邓小平江泽民胡锦涛关于中国共产党历...</div>
            <div>756</div>
          </div>
          <div class="table-row">
            <div>5</div>
            <div>毛泽东邓小平江泽民胡锦涛关于中国共产党历...</div>
            <div>638</div>
          </div>
        </div>
      </div>

      <!-- 党员信息 -->
      <div class="card">
        <div class="card-title">党员信息</div>
        <div class="stats-grid">
          <div class="stat-item">
            <div style="color: #FFD700; margin-bottom: 10px;">★</div>
            <div style="font-size: 14px; margin-bottom: 5px;">男性人员</div>
            <div class="stat-number">286</div>
            <div class="stat-label">66%</div>
          </div>
          <div class="stat-item">
            <div style="color: #FFD700; margin-bottom: 10px;">★</div>
            <div style="font-size: 14px; margin-bottom: 5px;">女性人员</div>
            <div class="stat-number">106</div>
            <div class="stat-label">34%</div>
          </div>
        </div>
      </div>

      <!-- 党员学历分布 -->
      <div class="card">
        <div class="card-title">党员学历分布</div>
        <div class="chart-container">
          <v-chart :option="educationChartOption" style="height: 100%;" />
        </div>
      </div>

      <!-- 特色活动风采 -->
      <div class="card">
        <div class="card-title">特色活动风采</div>
        <div class="photo-gallery">
          <div class="photo-item">活动照片1</div>
          <div class="photo-item">活动照片2</div>
          <div class="photo-item">活动照片3</div>
          <div class="photo-item">活动照片4</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import VChart from 'vue-echarts'
import { use } from 'echarts/core'
import {
  CanvasRenderer
} from 'echarts/renderers'
import {
  BarChart,
  LineChart,
  PieChart,
  RadarChart
} from 'echarts/charts'
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent,
  GridComponent
} from 'echarts/components'

use([
  CanvasRenderer,
  BarChart,
  LineChart,
  PieChart,
  RadarChart,
  TitleComponent,
  TooltipComponent,
  LegendComponent,
  GridComponent
])

// 党费收缴管理图表配置
const feeChartOption = ref({
  tooltip: {
    trigger: 'axis',
    backgroundColor: 'rgba(0, 0, 0, 0.8)',
    borderColor: '#FFD700',
    textStyle: { color: '#FFD700' }
  },
  grid: {
    left: '10%',
    right: '10%',
    top: '10%',
    bottom: '20%'
  },
  xAxis: {
    type: 'category',
    data: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12月'],
    axisLine: { lineStyle: { color: '#FFD700' } },
    axisLabel: { color: '#FFD700' }
  },
  yAxis: {
    type: 'value',
    max: 800,
    axisLine: { lineStyle: { color: '#FFD700' } },
    axisLabel: { color: '#FFD700' },
    splitLine: { lineStyle: { color: 'rgba(255, 215, 0, 0.2)' } }
  },
  series: [{
    data: [200, 300, 250, 400, 350, 450, 500, 600, 550, 650, 700, 750],
    type: 'line',
    smooth: true,
    lineStyle: { color: '#FFD700', width: 3 },
    itemStyle: { color: '#FFD700' },
    areaStyle: {
      color: {
        type: 'linear',
        x: 0, y: 0, x2: 0, y2: 1,
        colorStops: [
          { offset: 0, color: 'rgba(255, 215, 0, 0.3)' },
          { offset: 1, color: 'rgba(255, 215, 0, 0.1)' }
        ]
      }
    }
  }]
})

// 组织生活会及民主评议党员图表配置
const evaluationChartOption = ref({
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(0, 0, 0, 0.8)',
    borderColor: '#FFD700',
    textStyle: { color: '#FFD700' }
  },
  series: [{
    type: 'pie',
    radius: ['40%', '70%'],
    center: ['50%', '60%'],
    data: [
      { value: 60, name: '优秀', itemStyle: { color: '#FFD700' } },
      { value: 30, name: '不合格', itemStyle: { color: '#FFA500' } },
      { value: 10, name: '合格', itemStyle: { color: '#FF8C00' } }
    ],
    label: {
      color: '#FFD700',
      fontSize: 14
    },
    labelLine: {
      lineStyle: { color: '#FFD700' }
    }
  }]
})

// 主题党日开展情况图表配置
const partyDayChartOption = ref({
  tooltip: {
    trigger: 'axis',
    backgroundColor: 'rgba(0, 0, 0, 0.8)',
    borderColor: '#FFD700',
    textStyle: { color: '#FFD700' }
  },
  grid: {
    left: '15%',
    right: '10%',
    top: '10%',
    bottom: '20%'
  },
  xAxis: {
    type: 'category',
    data: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11月'],
    axisLine: { lineStyle: { color: '#FFD700' } },
    axisLabel: { color: '#FFD700' }
  },
  yAxis: {
    type: 'value',
    max: 800,
    axisLine: { lineStyle: { color: '#FFD700' } },
    axisLabel: { color: '#FFD700' },
    splitLine: { lineStyle: { color: 'rgba(255, 215, 0, 0.2)' } }
  },
  series: [{
    data: [400, 300, 350, 500, 450, 600, 550, 650, 700, 608, 750],
    type: 'bar',
    itemStyle: {
      color: {
        type: 'linear',
        x: 0, y: 0, x2: 0, y2: 1,
        colorStops: [
          { offset: 0, color: '#FFD700' },
          { offset: 1, color: '#FFA500' }
        ]
      }
    },
    barWidth: '60%'
  }]
})

// 理论学习情况图表配置
const studyChartOption = ref({
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(0, 0, 0, 0.8)',
    borderColor: '#FFD700',
    textStyle: { color: '#FFD700' }
  },
  series: [{
    type: 'pie',
    radius: ['30%', '60%'],
    center: ['50%', '50%'],
    data: [
      { value: 60, name: '分类1', itemStyle: { color: '#FFD700' } },
      { value: 28, name: '分类2', itemStyle: { color: '#FFA500' } },
      { value: 12, name: '分类3', itemStyle: { color: '#FF8C00' } }
    ],
    label: {
      color: '#FFD700',
      fontSize: 12
    }
  }]
})

// 组织生活图表配置
const orgLifeChartOption = ref({
  tooltip: {
    trigger: 'axis',
    backgroundColor: 'rgba(0, 0, 0, 0.8)',
    borderColor: '#FFD700',
    textStyle: { color: '#FFD700' }
  },
  grid: {
    left: '15%',
    right: '10%',
    top: '10%',
    bottom: '25%'
  },
  xAxis: {
    type: 'category',
    data: ['三会一课', '主题党日', '理论学习', '特色活动', '主题教育', '其他'],
    axisLine: { lineStyle: { color: '#FFD700' } },
    axisLabel: { 
      color: '#FFD700',
      rotate: 45,
      fontSize: 10
    }
  },
  yAxis: {
    type: 'value',
    max: 800,
    axisLine: { lineStyle: { color: '#FFD700' } },
    axisLabel: { color: '#FFD700' },
    splitLine: { lineStyle: { color: 'rgba(255, 215, 0, 0.2)' } }
  },
  series: [{
    data: [300, 400, 200, 500, 350, 606],
    type: 'bar',
    itemStyle: {
      color: {
        type: 'linear',
        x: 0, y: 0, x2: 0, y2: 1,
        colorStops: [
          { offset: 0, color: '#FFD700' },
          { offset: 1, color: '#FFA500' }
        ]
      }
    },
    barWidth: '50%'
  }]
})

// 党员学历分布图表配置
const educationChartOption = ref({
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(0, 0, 0, 0.8)',
    borderColor: '#FFD700',
    textStyle: { color: '#FFD700' }
  },
  radar: {
    indicator: [
      { name: '博士', max: 100, axisLabel: { color: '#FFD700' } },
      { name: '硕士', max: 100, axisLabel: { color: '#FFD700' } },
      { name: '本科', max: 100, axisLabel: { color: '#FFD700' } },
      { name: '大专', max: 100, axisLabel: { color: '#FFD700' } },
      { name: '中专', max: 100, axisLabel: { color: '#FFD700' } },
      { name: '高中', max: 100, axisLabel: { color: '#FFD700' } }
    ],
    axisLine: { lineStyle: { color: '#FFD700' } },
    splitLine: { lineStyle: { color: 'rgba(255, 215, 0, 0.3)' } },
    splitArea: { show: false },
    axisLabel: { color: '#FFD700', fontSize: 10 }
  },
  series: [{
    type: 'radar',
    data: [{
      value: [10, 30, 80, 60, 40, 20],
      itemStyle: { color: '#FFD700' },
      areaStyle: { 
        color: 'rgba(255, 215, 0, 0.2)',
        opacity: 0.3
      },
      lineStyle: { color: '#FFD700', width: 2 }
    }]
  }]
})

onMounted(() => {
  // 组件挂载后的初始化逻辑
})
</script>