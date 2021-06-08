<template>
    <div class="register">
        <LoginTop middleTop="登录"/>
        <LoginText label="姓名" class="name" 
            rule='^.{6,16}$'
            placeholder="请输入姓名"
            @inputChange="res => name = res"
        />
        <LoginText label="账号" class="count"
            rule='^.{6,16}$'
            placeholder="请输入账号"
            @inputChange="res => count = res"
        />
        <LoginText label="密码" class="password"
            rule='^.{6,16}$'
            placeholder="请输入密码"
            type="password"
            @inputChange="res => password = res"
        />

        <LoginBtn btntext="注册" @registerSubmit="registerSubmit"/>
    </div>
</template>

<script>
import LoginTop from '@/components/common/LoginTop.vue'
import LoginText from '@/components/common/LoginText.vue'
import LoginBtn from '@/components/common/LoginBtn.vue'
export default {
    data() {
        return {
            name: '',
            count: '',
            password: ''
        }
    },
    components: {
        LoginTop,
        LoginText,
        LoginBtn
    },
    methods: {
        registerSubmit() {
            if(this.name && this.count && this.password ) {
                console.log("正则校验成功！")
            }
        }
    }
}
</script>

<style lang="less">
    .register {
        .name {
            margin: 4.167vw 0;
        }
    }
</style>