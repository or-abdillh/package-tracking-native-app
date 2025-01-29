<template>
  <Page actionBarHidden="true" backgroundColor="#171717" style="padding: 36px;">
    <ScrollView>
      <StackLayout>
        <!-- header -->
        <FlexboxLayout height="70" justifyContent="space-between" marginBottom="16">
          <!-- avatar -->
          <FlexboxLayout width="45%" backgroundColor="#242424" borderRadius="16" alignItems="center" padding="8">

            <Image marginRight="12" src="~/assets/user.png" stretch="fill" width="50" height="50" borderRadius="10" />

            <StackLayout>
              <!-- user name -->
              <Label>
                <FormattedString>
                  <Span text="Stive Kote" style="color: white"></Span>
                </FormattedString>
              </Label>

              <!-- date -->
              <Label>
                <FormattedString>
                  <Span text="17 Jan, 2024" style="color: #6b7280;"></Span>
                </FormattedString>
              </Label>
            </StackLayout>
          </FlexboxLayout>

          <!-- coin -->
          <Label width="30%" backgroundColor="#242424" borderRadius="16" padding="8" textAlignment="center">
            <FormattedString marginRight="4">
              <Span text="872" style="color: #16a34a" fontWeight="medium" />
              <Span text=" " />
              <Span text="Coins" style="color: white;" />
            </FormattedString>
          </Label>
        </FlexboxLayout>

        <!-- search bar -->
        <FlexboxLayout height="70" justifyContent="space-between" alignItems="center" backgroundColor="#242424" borderRadius="16" paddingLeft="8" paddingRight="8" marginBottom="16">

          <FlexboxLayout alignItems="center" paddingLeft="12" width="80%">
            <Image src="~/assets/icons/search.png" width="16" height="16" marginRight="8" />
            <TextField hint="Track your package" backgroundColor="#242424" class="no-border" />
          </FlexboxLayout>

          <FlexboxLayout padding="4" alignItems="center" justifyContent="center" borderRadius="12" width="20%" height="50"  backgroundColor="#343434">
            <Image src="~/assets/icons/qr-code.png" width="20" height="20" stretch="fill" />
          </FlexboxLayout>
        </FlexboxLayout>

        <!-- banner -->
        <FlexboxLayout height="auto" backgroundColor="#4ade80" borderRadius="16" alignItems="center" justifyContent="space-between" paddingLeft="20" paddingTop="32" paddingRight="0" paddingBottom="32" marginBottom="16">
          <!-- copywriting -->
          <StackLayout width="50%">
            <Label paddingLeft="18">
              <FormattedString>
                <Span text="Discount" style="color: white;" fontSize="14" />
              </FormattedString>
            </Label>

            <Label paddingLeft="18">
              <FormattedString>
                <Span text="20% OFF" fontWeight="Bold" fontSize="32" style="color: white;" />
              </FormattedString>
            </Label>

            <Button backgroundColor="#171717" borderRadius="24" paddingLeft="12" paddingTop="2" paddingRight="12" paddingBottom="2">
              <FormattedString>
                <Span text="GET DISCOUNT" style="color: white" fontSize="12" />
              </FormattedString>
            </Button>
          </StackLayout>

          <!-- illustration -->
          <Image width="50%" src="~/assets/cardboard.png" stretch="fill" height="100" />
        </FlexboxLayout>

        <!-- menus -->
        <FlexboxLayout justifyContent="space-between" alignItems="center" marginBottom="24">
          <!-- price -->
          <FlexboxLayout height="70" width="24%" flexDirection="column" alignItems="center" justifyContent="center" backgroundColor="#242424" borderRadius="16" padding="4">
            <!-- icon -->
            <Image src="~/assets/icons/money-check.png" width="14" height="14" />
            <Label>
              <FormattedString>
                <Span text="Price" style="color: white;" />
              </FormattedString>
            </Label>
          </FlexboxLayout>

          <!-- point -->
          <FlexboxLayout height="70" width="24%" flexDirection="column" alignItems="center" justifyContent="center" backgroundColor="#242424" borderRadius="16" padding="4">
            <!-- icon -->
            <Image src="~/assets/icons/location-dot.png" width="12" height="14" />
            <Label>
              <FormattedString>
                <Span text="Point" style="color: white;" />
              </FormattedString>
            </Label>
          </FlexboxLayout>

          <!-- news -->
          <FlexboxLayout height="70" width="24%" flexDirection="column" alignItems="center" justifyContent="center" backgroundColor="#242424" borderRadius="16" padding="4">
            <!-- icon -->
            <Image src="~/assets/icons/news-paper.png" width="12" height="14" />
            <Label>
              <FormattedString>
                <Span text="News" style="color: white;" />
              </FormattedString>
            </Label>
          </FlexboxLayout>

          <!-- info -->
          <FlexboxLayout height="70" width="24%" flexDirection="column" alignItems="center" justifyContent="center" backgroundColor="#242424" borderRadius="16" padding="4">
            <!-- icon -->
            <Image src="~/assets/icons/circle-info.png" width="14" height="14" />
            <Label>
              <FormattedString>
                <Span text="Info" style="color: white;" />
              </FormattedString>
            </Label>
          </FlexboxLayout>
        </FlexboxLayout>

        <!-- Shipping -->
        <Flexboxlayout flexDirection="column">
          <!-- header -->
          <FlexboxLayout justifyContent="space-between" alignItems="center" marginBottom="12">
            <Label>
              <FormattedString>
                <Span text="Recent Shipping" fontSize="16" fontWeight="Bold" style="color: white;" />
              </FormattedString>
            </Label>

            <!-- navigate -->
            <FlexboxLayout justifyContent="space-between" alignItems="center">
              <Label marginRight="8">
                <FormattedString>
                  <Span text="See all" style="color: #16a34a;" />
                </FormattedString>
              </Label>

              <Image src="~/assets/icons/chevron-right.png" width="10" height="10" />
            </FlexboxLayout>
          </FlexboxLayout>

          <!-- list -->
          <Flexboxlayout flexDirection="column" backgroundColor="#242424" borderRadius="16" paddingTop="12" paddingBottom="12" paddingLeft="24" paddingRight="24">
            <ShippingList v-for="ship in shippings" :key="ship" :ship="ship" />
          </Flexboxlayout>
        </Flexboxlayout>
      </StackLayout>
    </ScrollView>
  </Page>
</template>

<script lang="ts">
  import { FlexboxLayout, FormattedString, Button, Image, SearchBar, StackLayout, TextField, ScrollView } from "@nativescript/core";
  import Vue from "nativescript-vue";
  import ShippingList from "./ShippingList.vue";

  export default Vue.extend({
    computed: {
      message() {
        return "Blank {N}-Vue app";
      }
    },
    components: {
      ShippingList
    },
    data() {
      return {

        shippings: [
          { id: "A425HYJ8", status: false },
          { id: "A153KOJ2", status: true },
          { id: "B672PLM9", status: true },
          { id: "C983QWE4", status: false },
          { id: "D234RTY7", status: true },
          { id: "E567UIO1", status: false },
          { id: "F890ASD3", status: true }
        ]
      }
    }
  });
</script>

<style scoped lang="scss">

  .no-border {
    border-bottom-width: 0;
    android-elevation: 0;
    background-color: transparent;
  }


</style>
