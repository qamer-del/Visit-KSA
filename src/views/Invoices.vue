<template>
    <div>
        <h1>Invoices</h1>
    </div>
</template>
<script>
import {onBeforeRouteLeave} from 'vue-router'
export default{
    
    setup(){
     onBeforeRouteLeave((to,form)=>{
        const answer = window.confirm('Are You sure You Want to leave this page? !')
        if (!answer) return false;
     })
    }
}
</script>