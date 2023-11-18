<template>
    <div>
    <router-link to="/cj">
            <img src="src/assets/抽奖.png" alt="抽奖" id="cj"/>
    </router-link>
    <router-link to="/tp">
        <img src="src/assets/投票.png" alt="投票" id="tp"/>
    </router-link>
    </div>
</template>

<script>

</script>

<style scoped>
#cj, #tp{
    position: absolute;
    top: 20vw;
    width: 35vw;
    border-radius: 2vw;
}
#cj:hover,#tp:hover{
    transform: scale(1.1);
    box-shadow: 0 1vw 1.2vw rgba(0,0,0,0.5);
}
#cj{
    left: 10vw;
}
#tp{
    right: 10vw;
}
</style>
