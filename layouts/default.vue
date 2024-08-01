<!-- header.vue -->
<template>
    <div>
        <header class="header">
            <som-logo></som-logo>
        </header>
        <Nuxt/>
        <footer>
            <div class="footer">
                <p>footer</p>
            </div>
        </footer>
    </div>

    
</template>

<script>
import SomLogo from '@/components/SomLogo.vue';

export default {
    components: {
        SomLogo,
    }
}
</script>

<style>
.header{
    height: 50px;
    background-color: #FFE7CC;
}
.footer{
    height: 50px;
    background-color: #F9F9F9;
}

</style>
