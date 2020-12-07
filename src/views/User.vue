<template>
    <div>
        <table>
            <tr>
                <td>编号</td>
                <td>姓名</td>
                <td>性别</td>
                <td>地址</td>
                <td>QQ号</td>
                <td>邮箱</td>
            </tr>
            <tr v-for="item in users">
                <td>{{item.id}}</td>
                <td>{{item.name}}</td>
                <td>{{item.gender}}</td>
                <td>{{item.add }}</td>
                <td>{{item.qq}}</td>
                <td>{{item.email}}</td>
            </tr>
        </table>
    </div>
</template>

<script>
    export default {
        name: "User",
        data(){
            return{
                msg:'HelloVue',
                users:[
                    // {
                    //     id:1,
                    //     name:'张三',
                    //     gender:'男',
                    //     address:'北京',
                    //     qq:'7878878',
                    //     email:'78855@qq.com'
                    // },
                    // {
                    //     id:2,
                    //     name:'王二',
                    //     gender:'女',
                    //     address:'上海',
                    //     qq:'738389383',
                    //     email:'7885556465@qq.com'
                    // },
                    // {
                    //     id:3,
                    //     name:'李四',
                    //     gender:'男',
                    //     address:'广州',
                    //     qq:'468541698465',
                    //     email:'19685165@qq.com'
                    // },
                    // {
                    //     id:4,
                    //     name:'王五',
                    //     gender:'女',
                    //     address:'深圳',
                    //     qq:'686798798',
                    //     email:'34567@qq.com'
                    // },
                    // {
                    //     id:5,
                    //     name:'靳文雅',
                    //     gender:'女',
                    //     address:'河南',
                    //     qq:'7798468549846546',
                    //     email:'874985465465@qq.com'
                    // }
                ]

            }
        },
        //初始化操作
        created() {
            const _this = this
            axios.get('http://localhost:8181/user/findAll').then(function(response){
                _this.users=response.data
            })
        }
    }
</script>

<style scoped>

</style>