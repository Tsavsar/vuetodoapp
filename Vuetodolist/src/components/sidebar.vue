<script setup>
    import { reactive, ref } from 'vue';
import todolistVue from './todolist.vue';

    const open = ref(false)

    function toggle(){
        open.value = !open.value
    }

    const openmenu = ref('open')

</script>

<template>

    <div class="menu" @click="toggle()" >
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
            <path d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg>
    </div>
    <template v-if="open">
<div class="side-bar" >
    <div class="profile-cont" >
<h1 class="username" >
    Micheal Cera
</h1>
<p class="tasks" >
Tasks:{todos.length}
</p>
<p class="comp-tasks" >
Tasks Completed:
</p>
    </div>
    <div class="setting" @click="toggle()" >
    <div class=" white" >
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512" width="35" height="35" >
            <path d="M310.6 150.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L160 210.7 54.6 105.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L114.7 256 9.4 361.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L160 301.3 265.4 406.6c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L205.3 256 310.6 150.6z"/></svg>
    </div>
    <br>
    <div class="white">
        <svg xmlns="http://www.w3.org/2000/svg"
        id="Outline" viewBox="0 0 24 24" width="25" height="25">
        <path d="M1,4.75H3.736a3.728,3.728,0,0,0,7.195,0H23a1,1,0,0,0,0-2H10.931a3.728,3.728,0,0,0-7.195,0H1a1,1,0,0,0,0,2ZM7.333,2a1.75,1.75,0,1,1-1.75,1.75A1.752,1.752,0,0,1,7.333,2Z"/><path
        d="M23,11H20.264a3.727,3.727,0,0,0-7.194,0H1a1,1,0,0,0,0,2H13.07a3.727,3.727,0,0,0,7.194,0H23a1,1,0,0,0,0-2Zm-6.333,2.75A1.75,1.75,0,1,1,18.417,12,1.752,1.752,0,0,1,16.667,13.75Z"/><path
        d="M23,19.25H10.931a3.728,3.728,0,0,0-7.195,0H1a1,1,0,0,0,0,2H3.736a3.728,3.728,0,0,0,7.195,0H23a1,1,0,0,0,0-2ZM7.333,22a1.75,1.75,0,1,1,1.75-1.75A1.753,1.753,0,0,1,7.333,22Z"/></svg>

    </div>
</div>
</div>
</template>
</template>
<script>
    import child from './todolist.vue'
    // export default{
    //     name: 'app',
    
</script>

<style scoped>
    .side-bar{
        background-color: #008DFF;
        border-radius: 0px 35px 0px 0px;
        height: 100%;
        width: 80%;
        position: absolute;
        top: 0;
        left: 0;
        z-index: 1;
        overflow-x: hidden;
        overflow-y: hidden;
        transition: 0.5s;
    }
    .profile-cont{
        color: #ffffff;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding-top: 160px;

}
    .username{
        font-weight: 600;
        font-size: 32px;
        font-family: 'Inter';
font-style: normal;
font-weight: 600;
line-height: 39px;
color: #ffffff;
}
    .tasks, .comp-tasks{
        font-weight: 600;
        font-size: 20px;
        font-family: 'Inter';
font-style: normal;
font-weight: 600;
}
.setting{
    margin-top: 155%;
    margin-left: 85%;
}
.white{
    fill: #ffffff;
    width: 35px;
height: 35px;
}

.menu{
    width: 20px;
height: 10px;
fill: #808080;
margin-top: 10px;
}

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    overflow: hidden;
}
</style>
