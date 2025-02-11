<template>
    <div class="page-footer" v-if="!disableFooter">
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
            return this.userConfig?.footerLink || 'https://github.com/jinnan11/CloudFlare-ImgBed'
        },
        thisYear() {
            return new Date().getFullYear()
        },
        disableFooter() {
            return this.userConfig?.disableFooter || false
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
    color: var(--page-footer-text-color);
    font-size: large;
    user-select: none;
}
@media (max-width: 768px) {
    .page-footer {
        font-size: small;
    }
}
.footer-name {
    color: var(--page-footer-name-color);
    font-weight: bold;
    text-decoration: none;
}
.footer-link-icon {
    color: var(--page-footer-name-color);
    margin-left: 5px;
}
</style>
