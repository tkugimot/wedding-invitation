<template>
        <v-footer
                v-bind="localAttrs"
                :padless="padless"
                class="red lighten-4 text-center"
        >
            <v-card
                    flat
                    tile
                    width="100%"
                    class="red lighten-4 text-center"
            >
                <v-card-text>
                    <v-btn
                            v-for="icon in icons"
                            :key="icon"
                            class="mx-4"
                            icon
                            v-smooth-scroll
                            href="#top"
                            color="red"
                    >
                        <v-icon size="38px" href="#top">
                            {{ icon }}
                        </v-icon>
                    </v-btn>
                </v-card-text>

                <v-divider></v-divider>

                <v-card-text class="black--text">
                    Icon made by Freepik from www.flaticon.com<br>
                    background image made by <a href="https://pixabay.com/ja/users/prawny-162579/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=2090137">Prawny</a> from <a href="https://pixabay.com/ja/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=2090137">Pixabay</a>
                    <br><br> © {{ new Date().getFullYear() }}
                    <strong>Toshimitsu Kugimoto</strong>
                </v-card-text>
            </v-card>
        </v-footer>
</template>

<style scoped>
    .black--text {
        font-family: "Waltograph 42";
        font-size: 18px;
    }
</style>
<script>
    export default {
        data: () => ({
            icons: [
                'mdi-arrow-up-box',
            ],
            items: [
                'default',
                'absolute',
                'fixed',
            ],
            padless: false,
            variant: 'default',
        }),
        computed: {
            localAttrs () {
                const attrs = {}

                if (this.variant === 'default') {
                    attrs.absolute = false
                    attrs.fixed = false
                } else {
                    attrs[this.variant] = true
                }
                return attrs
            },
        },
    }
</script>

