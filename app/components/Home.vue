<template>
  <Page actionBarHidden="true" backgroundColor="#171717" style="padding: 36px;">
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
        <SearchBar hint="Track your package" backgroundColor="#242424" width="80%" textFieldHintColor="red" />

        <FlexboxLayout padding="4" alignItems="center" justifyContent="center" borderRadius="12" width="20%" height="50"  backgroundColor="#343434">
          <Image src="~/assets/icons/qr-code.png" width="20" height="20" stretch="fill" />
        </FlexboxLayout>
      </FlexboxLayout>

      <!-- banner -->
      <FlexboxLayout height="auto" backgroundColor="#4ade80" borderRadius="16" alignItems="center" justifyContent="space-between" paddingLeft="20" paddingTop="32" paddingRight="0" paddingBottom="32">
        <!-- copywriting -->
        <StackLayout width="50%">
          <Label paddingLeft="18">
            <FormattedString>
              <Span text="Discount" style="color: white;" />
            </FormattedString>
          </Label>

          <Label paddingLeft="18">
            <FormattedString>
              <Span text="20% OFF" fontWeight="Bold" fontSize="24" style="color: white;" />
            </FormattedString>
          </Label>

          <Button backgroundColor="#171717" borderRadius="24" paddingLeft="16" paddingTop="4" paddingRight="16" paddingBottom="4">
            <FormattedString>
              <Span text="GET DISCOUNT" style="color: white" fontSize="12" />
            </FormattedString>
          </Button>
        </StackLayout>

        <!-- illustration -->
        <Image width="50%" src="~/assets/cardboard.png" stretch="fill" height="100" />
      </FlexboxLayout>
    </StackLayout>
  </Page>
</template>

<script lang="ts">
  import { FlexboxLayout, FormattedString, Button, Image, SearchBar, StackLayout } from "@nativescript/core";
import Vue from "nativescript-vue";

  export default Vue.extend({
    computed: {
      message() {
        return "Blank {N}-Vue app";
      }
    }
  });
</script>

<style scoped lang="scss">

</style>
