<template>
        <v-footer
                v-bind="localAttrs"
                :padless="padless"
                class="red lighten-1 text-center"
        >
            <v-card
                    flat
                    tile
                    width="100%"
                    class="red lighten-1 text-center"
            >
                <v-card-text>
                    <v-btn
                            v-for="icon in icons"
                            :key="icon"
                            class="mx-4"
                            icon
                            v-smooth-scroll
                            href="#top"
                    >
                        <v-icon size="24px" href="#top">
                            {{ icon }}
                        </v-icon>
                    </v-btn>
                </v-card-text>

                <v-divider></v-divider>

                <v-card-text class="white--text">
                    © {{ new Date().getFullYear() }} <strong>Toshimitsu Kugimoto</strong>
                </v-card-text>
            </v-card>
        </v-footer>
</template>

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

