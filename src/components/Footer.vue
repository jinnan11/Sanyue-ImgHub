<template>
    <div class="page-footer">
        <p>© 2025 <a class="footer-name" href="https://github.com/jinnan11" target="_blank">槿南</a>
            <a :href="footerLink" target="_blank">
                <font-awesome-icon icon="paper-plane" class="footer-link-icon"/>
            </a>
        </p>
    </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
    name: 'Footer',
    computed: {
        ...mapGetters(['userConfig']),
        footerLink() {
            return this.userConfig?.footerLink || 'https://jinnan.top'
        }
    }
}
</script>

<style scoped>
.page-footer {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    color: aliceblue;
    font-size: large;
    user-select: none;
}
.footer-name {
    color: antiquewhite;
    font-weight: bold;
    text-decoration: none;
}
.footer-link-icon {
    color: antiquewhite;
    margin-left: 5px;
}
</style>
