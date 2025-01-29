<template>
    <FlexboxLayout justifyContent="space-between" alignItems="center" paddingBottom="12" paddingTop="12" class="container" marginBottom="4">
        <!-- start -->
        <Flexboxlayout alignItems="center">
            <!-- icon -->
            <FlexboxLayout width="40" height="40" borderRadius="20" justifyContent="center" alignItems="center" :backgroundColor="ship.status ? '#86efac' : '#fdba74'">
                <Image src="~/assets/icons/box.png" width="20" height="20" />
            </FlexboxLayout>

            <!-- detail -->
            <Flexboxlayout marginLeft="24" flexDirection="column">
                <Label>
                    <FormattedString>
                        <Span text="ID NUMBER" fontSize="10" style="color: #d1d5db;" />
                    </FormattedString>
                </Label>

                <Label>
                    <FormattedString>
                        <Span :text="ship.id" fontSize="16" style="color: #e5e7eb;" />
                    </FormattedString>
                </Label>
            </Flexboxlayout>
        </Flexboxlayout>

        <!-- end -->
        <Label>
            <FormattedString>
                <Span fontSize="12" :text="ship.status ? 'Completed' : 'On the way'" :style="{ color: ship.status ? '#86efac' : '#fdba74' }" />
            </FormattedString>
        </Label>
    </FlexboxLayout>
</template>

<script>

import { FlexboxLayout, FormattedString, Image, Label, Span } from "@nativescript/core";
import Vue from "nativescript-vue";

export default Vue.extend({
    props: {
        ship: {
            id: String,
            status: Boolean
        }
    }
});

</script>

<style scoped>

.container {
    border-bottom-width: 2px;
    border-bottom-color: #343434;
}

</style>
