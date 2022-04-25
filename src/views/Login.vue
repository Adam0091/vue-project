<script setup>
    import { reactive, ref } from "@vue/reactivity";
    import { login } from '../composibles/user';
    import { useRouter } from 'vue-router';

    const router = useRouter();

    const isAuth = ref(null);
    isAuth.value = localStorage.getItem("token") ? true : false;
    if(isAuth.value) {
      router.push({name: 'home'})
    }
    const user = reactive({
      email: "",
      password: "",
    });

    const signin = () => {
      const response = login(user, "sigin");
      localStorage.setItem("token", response);
    }
</script>

<template>
    <div class="auth">
        <div class="">{{user}}</div>
        <div class="form">
            <div class="form-control">
                <label for="login">Login</label>
                <input type="text" id="login" name="login" v-model="user.email">
            </div>
            <div class="form-control">
                <label for="password">Login</label>
                <input type="password" id="password" name="password" v-model="user.password">
            </div>
            <button @click="signin">sign in</button>
        </div>
    </div>
</template>

<style scoped>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.auth {
    height: 100vh;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}
.form {
    max-width: 400px;

}
</style>