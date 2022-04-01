<div class='container'>
    <div class="content display_flex flex-wrap_wrap">
        <div class="content-item" 
             v-for="(item, index) in list" :key="index">
            <ul class="display_flex flex-direction_column"
                 v-show="isOpen || index < max">
                <li class="label"><span>{{ item.label }}</span></li>
                <li class="value"><span>{{ item.value }}</span></li>
            </ul>
        </div>
    </div>
    <button v-show="!isOpen && list.length > max" @click="isOpen = !isOpen">展开全部信息</button>
    <button v-show="isOpen && list.length > max" @click="isOpen = !isOpen">收起</button>
</div>
export default {
    data () {
        return {
            max: 6, // 默认最多显示的个数；最大行数*每行显示的个数 Number 
            isOpen: false, // 是否展开全部信息的标识 Boolean 默认false
            list:[
                {label: '初登日期', value: '2005-10-20'},
                {label: '出厂日期', value: '2014-11'},
                {label: '使用性质', value: '非营运'},
                {label: '车辆注册地', value: '北京-北京市-昌平区'},
                {label: '表显里程', value: '3.1万公里'},
                {label: '排放标准', value: '国四'},
                {label: '排量', value: '3.3'},
                {label: '变速箱形式', value: 'AT'},
                {label: '座位数', value: '5'}
            ]
        }
    }
}
