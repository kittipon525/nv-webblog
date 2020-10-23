<template>
    <div>
        <div class="nv-navbar">
            <ul class="nav">
                <li><router-link :to="{name: 'products'}" >รายการสินค้า</router-link></li>
                <li><router-link :to="{name: 'users'}" >ผู้ใช้</router-link></li>
                <li><router-link :to="{name: 'login'}" >เข้าสู่ระบบบ</router-link></li>
                <li><a v-on:click.prevent="logout" href="#">ออกจากระบบ</a></li>
            </ul>
            <div class="clearfix"></div>
        </div>
    </div>
</template>
<script>
export default {
    methods: {
        logout () {
            this.$store.dispatch('setToken', null)
            this.$store.dispatch('setUser', null)
            this.$router.push({
                name: 'login'
            })
        }
    }
}
</script>
<style scoped>
    .nv-navbar {
        background-color:rgb(72, 72, 73);
        width: 100%;
        padding:10px 0px 10px 0px;
    }
    .nv-navbar .nav {
        list-style: none;
        margin:0;
        padding:0;
        float:left;
    }
    .nv-navbar .nav li {
        float:left;
    }
    .nv-navbar .nav li a {
        padding: 10px;
        text-decoration: none;
        color:rgb(101, 255, 147);
        font-weight: bold;
    }
    .nv-navbar .nav li a:hover {
        padding: 10px;
        text-decoration: none;
        color:darkslategrey;
    }
    .nv-navbar .nav li a.router-link-active {
        background-color:rgb(223, 221, 215);
        color:darkslategrey;
    }
    .clearfix {
        clear: left;
    }
</style>