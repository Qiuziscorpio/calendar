<template>
  <div class="picker" v-show="isShowView"> 
    <!-- 日历控件 -->
    <div class="picker-head">
    </div>
    <div class="picker-content" >
      <div class="picker-content-head">
        <span @click="onCancel">取消</span>
        <span @click="onConfirm">确定</span>
      </div>
      <div class="calendar">
        <div class="calendar-head">
          <!-- 星期几 -->
          <div class="calendar-week-title">
            <span class="calenda-week" v-for="item in weeks" :key="'w' + item" 
            :class="(item === '日' || item === '六') ? 'calendar-saturdaytomonday' : ''">
              {{item}}
            </span>                                                                                 
          </div>
        </div>
        <!-- 日历内容 -->
        <div class="calendar-content">
          <!-- 年月 -->
          <!-- <div class="calendar-years-title">2018年08月</div>
          <table class="calendar-table" cellspacing="0">
            <tbody class="calendar-tbody">
              <tr class="calendar-tr">
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days"></span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days"></span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days"></span>
                  </div>
                </td>              
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days calendar-cell-selected">1</span>
                    <span class="calendar-cell-tag">入住</span>
                  </div>
                </td>              
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days calendar-cell-selecteds">2</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days calendar-cell-selecteds">3</span>
                  </div>
                </td>              
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days calendar-cell-selected">4</span>
                    <span class="calendar-cell-tag">离店</span>
                  </div>
                </td>           
              </tr> 
              <tr class="calendar-tr">
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days calendar-saturdaytomonday">5</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">6</span>
                  </div>
                </td>
                <td class="calendar-cell">
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">7</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">8</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">9</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">10</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days calendar-saturdaytomonday">11</span>
                  </div>
                </td>            
              </tr>  
              <tr class="calendar-tr">
                <td>
                  <div class="calendar-cell ">
                    <span class="calendar-cell-days calendar-saturdaytomonday">12</span>
        
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">13</span>
                  </div>
                </td>
                <td class="calendar-cell">
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">14</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">15</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">16</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days">17</span>
                  </div>
                </td>
                <td>
                  <div class="calendar-cell">
                    <span class="calendar-cell-days calendar-saturdaytomonday">18</span>
                  </div>
                </td>            
              </tr>  
              <tr class="calendar-tr">
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days calendar-saturdaytomonday">19</span>
          
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">20</span>
                    </div>
                  </td>
                  <td class="calendar-cell">
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">21</span>
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">22</span>
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">23</span>
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">24</span>
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days calendar-saturdaytomonday">25</span>
                    </div>
                  </td>            
                </tr>
                <tr class="calendar-tr">
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days calendar-saturdaytomonday">26</span>
          
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">27</span>
                    </div>
                  </td>
                  <td class="calendar-cell">
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">28</span>
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">29</span>
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">30</span>
                    </div>
                  </td>
                  <td>
                    <div class="calendar-cell">
                      <span class="calendar-cell-days">31</span>
                    </div>
                  </td>         
                </tr>                                               
            </tbody>
          </table> -->
          <div v-for="(item, mIndex) in dateIiem" :key="'m'+mIndex">
            <div class="calendar-years-title">{{item.year}}年{{item.month}}月</div>
            <table class="calendar-table" cellspacing="0">
              <tbody class="calendar-tbody">
                <tr class="calendar-tr" v-for="(date, wIndex) in item.weeks" :key="'w'+wIndex" >
                  <td v-for="(day, dIndex) in date" :key="'d'+dIndex">
                    <div class="calendar-cell calendar-cell-disabled"  v-if="day.disabled">
                      <span class="calendar-cell-days">{{day.day}}</span>
                      <span class="calendar-cell-tag" v-if="day.tag">{{day.tag}}</span>
                    </div>
                    <div class="calendar-cell" v-else>
                      <span class="calendar-cell-days calendar-cell-selected" v-if="day.selected">{{day.day}}</span>
                      <span class="calendar-cell-days calendar-cell-selecteds" v-else-if="day.selecteds" @click="setSelect(mIndex, item, wIndex, dIndex, day.day)">{{day.day}}</span>
                      <span class="calendar-cell-days" 
                      v-else
                      :class="(day.week === '日' || day.week === '六') ? 'calendar-saturdaytomonday' : ''"  
                      @click="setSelect(mIndex, item, wIndex, dIndex, day.day)">{{day.day}}</span>
                      <span class="calendar-cell-tag" v-if="day.tag">{{day.tag}}</span>
                    </div>                    
                  </td>          
                </tr>                                             
              </tbody>
            </table> 
          </div>          
        </div>
      </div>     
    </div> 
    <div class="picker-shade"></div> 
  </div>
</template>
<script>

export default {
  name: 'calendar',

  props: {
    isShow: {
      type: Boolean,
      default: false
    },
    selectedDate: {
      type: Array,
      default: function () {
        return []
      }
    }
  },

  watch: {
    'isShow' (val) {
      this.isShowView = val
    },
    'isShowView' (val) {
      if (this.$parent.$refs.smPage) {
        if (val) {
          this.$parent.$refs.smPage.style = 'overflow: hidden; height: 48vh'
        } else {
          this.$parent.$refs.smPage.style = ''
        }
      }
    }
  },

  data () {
    return {
      isShowView: this.isShow,
      weeks: ['日', '一', '二', '三', '四', '五', '六'],
      dateIiem: [],
      currentDate: this.selectedDate,
      selectCount: this.selectedDate.length,
      isSelect: false
    }
  },

  mounted () {
    this.getDate()
  },

  methods: {
    onCancel () {
      this.isShowView = false
      this.$emit('onCancel', '取消')
      this.$emit('update:isShow', false)
    },
    onConfirm () {
      if (this.isSelect) {
        this.$vux.toast.text('请选择日期')
        return
      }
      this.isShowView = false
      this.$emit('update:isShow', false)
      this.$emit('onConfirm', this.currentDate)
    },
    mGetDate (year, month) {
      var d = new Date(year, month, 0)
      return d.getDate()
    },
    getDate (m) {
      let months = []
      let currentDate = new Date()
      // 当前年月日
      let Y = currentDate.getFullYear()
      let M = currentDate.getMonth()
      let D = currentDate.getDate()
      // 指定日子后的年月日2个月后
      let futureDate = m || new Date()
      futureDate.setMonth(futureDate.getMonth() + 3)
      let _Y = futureDate.getFullYear()
      let _M = futureDate.getMonth()

      // 当一定天数之后的日期还是今年时
      if (Y === _Y) {
        for (var n = M; n < _M; n++) {
          months.push({
            year: Y,
            month: n + 1,
            monthNumber: this.mGetDate(Y, n + 1),
            firstDay: '',
            weeks: []
          })
        }
      }
      months.map((res, index) => {
        let days = []

        // 计算每个月的第一天为星期几
        let f = new Date(res.year, res.month - 1, 1)
        res.firstDay = this.weeks[f.getDay()]

        // 计算每个月的天数
        for (let d = 0; d < res.monthNumber; d++) {
          let _day = d + 1
          let _dd = new Date(res.year, res.month - 1, _day)
          let getDay = this.weeks[_dd.getDay()]
          let disabled = false
          let selected = false
          let tag = ''
          let selecteds = false

          // 当前月 计算不可点击的日期 时间从当前系统时间开始算起
          if (index === 0) {
            if (_day < D) {
              disabled = true
            }
          }
          // 计算当前所选月份和天
          this.selectedDate.map((s, i) => {
            let m = parseInt(s.value.split('-')[0]) // 当前所选的月份
            let d = parseInt(s.value.split('-')[1]) // 当前所选的天
            if (m === res.month) {
              if (d === _day) {
                tag = s.key
                selected = true
              }
            }
          })

          // 多选时
          if (this.selectedDate.length > 1) {
            let m = parseInt(this.selectedDate[0].value.split('-')[0])
            let d = parseInt(this.selectedDate[0].value.split('-')[1])
            let m2 = parseInt(this.selectedDate[1].value.split('-')[0])
            let d2 = parseInt(this.selectedDate[1].value.split('-')[1])
            // 计算当当前的天数大于原来选择的天数数量超过2以上
            if (((d2 - d) > 1) || m2 > m) {
              if (res.month === m || res.month === m2) {
                if (_day > d && _day < d2) {
                  selecteds = true
                } else {
                  if (m !== m2) {
                    if ((m2 === res.month) && (d2 > _day)) {
                      selecteds = true
                    }
                    if (_day > d) {
                      selecteds = true
                    }
                  }
                }
              }
            }
          }

          days.push({
            week: getDay,
            day: _day,
            disabled: disabled,
            selected: selected,
            tag: tag,
            selecteds: selecteds
          })
        }
        // 将每个月每周区分
        let allWeek = []
        let arr = []
        days.forEach((item, index) => {
          arr.push(item)
          if (item.week === '六' || index === (days.length - 1)) {
            allWeek.push(arr)
            arr = []
          }
          if (allWeek[0]) {
            if (allWeek[0].length < 7) {
              allWeek[0].unshift(0, '', 7 - allWeek[0].length)
            }
          }
        })
        res.weeks = allWeek
      })
      this.dateIiem = months
    },
    formatDate (m, d) {
      let newM = m > 10 ? m : `0${m}`
      let newD = d > 9 ? d : `0${d}`
      return `${newM}-${newD}`
    },
    setSelect (mIndex, item, wIndex, dIndex, day) {
      // 设置当前所选的日期
      let current = this.dateIiem[mIndex].weeks[wIndex][dIndex]
      let sData = this.selectedDate[0]
      let sData2 = this.selectedDate[1]
      let oldM = parseInt(this.currentDate[0].value.split('-')[0]) || ''
      let oldD = parseInt(this.currentDate[0].value.split('-')[1]) || ''
      ++this.selectCount
      if (this.selectCount > this.currentDate.length || (oldM === item.month && day < oldD)) {
        this.removeSelect(item.month, day, sData.key)
        current.tag = sData.key
      } else {
        if (oldM > item.month && day > oldD) {
          this.removeSelect(item.month, day, sData.key)
          current.tag = sData.key
        } else {
          current.tag = sData2.key
          this.currentDate[1] = {
            value: this.formatDate(item.month, day),
            key: sData2.key
          }
          // 计算当当前的天数大于原来选择的天数数量超过2以上
          if (((day - oldD) > 1) || item.month > oldM) {
            this.dateIiem.map(m => {
              m.weeks.map(w => {
                w.map(d => {
                  if (typeof d === 'object') {
                    if (m.month === oldM || m.month === item.month) {
                      if (d.day > oldD && d.day < day) {
                        d.selecteds = true
                      } else {
                        if (oldM !== item.month) {
                          if ((item.month === m.month) && (day > d.day)) {
                            d.selecteds = true
                          }
                          if (d.day > oldD) {
                            d.selecteds = true
                          }
                          return
                        }
                        d.selecteds = false
                      }
                    }
                  }
                })
              })
            })
          }
          this.isSelect = false
        }
      }
      current.selected = true
    },
    removeSelect (m, d, k) {
      this.dateIiem.map(m => {
        m.weeks.map(w => {
          w.map(d => {
            if (typeof d === 'object') {
              d.selected = false
              d.selecteds = false
              d.tag = ''
            }
          })
        })
      })
      this.selectCount = 1
      this.isSelect = true
      this.currentDate[0] = {
        value: this.formatDate(m, d),
        key: k
      }
    }
  }
}
</script>

<style lang="less" scoped>
  @import '../styles/calendar';
</style>


