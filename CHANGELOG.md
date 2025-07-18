# Braintree Android Drop-In Release Notes

## unreleased

* Fix lifecycle crashes (fixes #494, #487, #404, #403, #379, #356)

## 6.17.0

* Bump braintree_android module dependency versions to `4.50.0`

## 6.16.0

* Bump braintree_android module dependency versions to `4.45.0`
* Fixes Google Play Store Rejection
  * Add `hasUserLocationConsent` property to `DropInRequest`
  * Deprecate existing constructor that does not pass in `hasUserLocationConsent`

## 6.15.0

* Refresh vaulted payment methods list after 3DS is canceled (fixes #455)
* Bump braintree_android module dependency versions to `4.41.0`

## 6.14.0

* Bump braintree_android module dependency versions to `4.40.1`
* Fix NPE when `DropInListener` is null

## 6.13.0

* Bump braintree_android module dependency versions to `4.38.2`
* Android 14 Support
  * Upgrade `compileSdkVersion` and `targetSdkVersion` to API 34
* Add `customUrlScheme` property to `DropInRequest` to allow for custom URL schemes to be set for browser-based flow deep links

## 6.12.0

* Add `PaymentMethodClient` with API `getPaymentMethodNonces` and `deletePaymentMethod`
* Bump braintree_android module dependency versions to `4.37.0`

## 6.11.1

* Reset bundle arguments for AddCardFragment after prefill card text is applied to Card Form (fixes #429)

## 6.11.0

* Add California Privacy Laws notice of collection to credit card form
* Add `DropInRequest.setCardLogosDisabled()` to hide card logos on the credit card form if desired

## 6.10.0

* Bump braintree_android module dependency versions to `4.33.0`

## 6.9.0

* Prevent Google Pay from launching twice when double tapped
* Bump braintree_android module dependency versions to `4.27.0`

## 6.8.1

* Dismiss keyboard and submit form on Card Details when form is complete and `Enter` is pressed
* Fix bug where payment methods can be selected multiple times

## 6.8.0

* Bump braintree_android module dependency versions to `4.26.0`
* Fix issue that causes the DropIn UI to hang when a duplicate payment method is entered and user returns to Bottom Sheet view (fixes #370)

## 6.7.0

* Bump braintree_android module dependency versions to `4.23.1`

## 6.6.0

* Bump braintree_android module dependency versions to `4.23.0`

## 6.5.1

* Fix issue that caused Add Card button to attempt tokenization multiple times when double tapped.

## 6.5.0

* Add `DropInClient#invalidateClientToken()` method (fixes #367)
* Bump braintree_android module dependency versions to `4.20.0` (fixes #371)

## 6.4.0

* Bump braintree_android module dependency versions to `4.19.0`
* Notify merchant via error message the payment method is duplicated (fixes #357)
* Android 13 Support
* Upgrade `targetSdkVersion` and `compileSdkVersion` to API 33
* Collect device data for Card payments that aren't using 3D Secure (fixes #364)

## 6.3.0

* Deprecate constructors that require a `DropInRequest`.
* Add DropInClient#launchDropIn(DropInRequest) method.

## 6.2.0

* Check if BottomSheetFragment is visible using Android Fragment API (fixes #348)
* Fix issue where `UserCanceledException` was not being sent on bottom sheet dismissal (fixes #346)
* Bump braintree_android module dependency versions to `4.12.0`
* Add `launchDropIn()` method
* Deprecate `launchDropInForResult(Activity, Int)` in favor of `launchDropIn()` method

## 6.1.0

* Update Vault Manager inline documentation 
* Add `ClientTokenProvider` interface for asynchronously fetching client token authorization
* Add new `DropInClient` constructors that accept `ClientTokenProvider` or tokenization key string
* Deprecate `DropInClient` constructor that accepts `Context` in favor of new constructors
* Bump braintree_android module dependency versions to `4.10.1`
* Bump `card-form` to `5.4.0`

## 6.0.2

* Bump braintree_android module dependency versions to `4.8.1`

## 6.0.1

* Check if `BottomSheetPresenter` is null before unbinding in `BottomSheetFragment` (fixes #319)

## 6.0.0

* Bump braintree_android module dependency versions to `4.7.0`
* Bump `card-form` to `5.3.0`
* Localization
  * Add support for Czech, Greek, Finnish, Hebrew, Hungrian, and Slovak localization
* Venmo
  * Add `VenmoRequest` setter to `DropInRequest`
  * Don't show Venmo payment method option when Venmo not installed on device
* CardForm
  * Focus Cardholder Name field when adding card details if field not disabled (fixes #180)
* DropInRequest
  * Set explicit class loader for `DropInRequest` (fixes #191)
  * Wrap `DropInRequest` in Parcelable bundle (fixes #228)
* Accessibility
  * Increase color contrast and add content descriptions for screen readers
* Breaking Changes
  * Language Support
    * Require Java 8 or higher
  * Localization
    * Remove support for Turkish localization
  * Visibility
    * Make `BottomSheetState` package-private
    * Make `DropInEventType` package-private
    * Make `DropInActivity#onError` package-private
    * Make `AnimatedButtonView` package-private
    * Make `PaymentMethodItemView` package-private
    * Make `SupportedPaymentMethodsViewHolder` package-private
    * Make `VaultedPaymentMethodSelectedListener` package-private
    * Make static strings in `DropInClient` package-private
    * Make `DropInClient#deliverBrowserSwitchResult` package-private
    * Make `DropInResultCallback` package-private
    * Make `PaymentMethodDeleteException` package-private
  * Venmo
    * Remove `vaultVenmo` on `DropInRequest` in favor of setting `shouldVault` on `VenmoRequest`
  * DropInPaymentMethod
    * Rename `DropInPaymentMethodType` to `DropInPaymentMethod`
  * DropInRequest
    * Remove `requestThreeDSecureVerification` from `DropInRequest`

## 6.0.0-beta2

* Android 12 Support
  * Bump braintree_android module dependency versions to `4.6.0`
  * Upgrade `targetSdkVersion` and `compileSdkVersion` to API 31
  * Fix issue where Venmo app is not detected on Android 12 devices
* Breaking Changes
  * DropInRequest
    * Remove `collectDeviceData` from `DropInRequest` in favor of always returning device data on `DropInResult`

## 6.0.0-beta1

* Dependencies
  * Include `braintree-core`, `three-d-secure`, `paypal`, `venmo`, `google-pay`, `card`, `data-collector`, and `union-pay` as api
  * Bump `card-form` to `5.2.0`
* DropInClient
  * Add `DropInClient`
  * Add `DropInResultCallback`
  * Add `FetchMostRecentPaymentMethodCallback`
  * Add `GetSupportedCardTypesCallback`
* Fragment Architecture
  * Add `SupportedPaymentMethodsFragment`
  * Add `BottomSheetFragment`
  * Add `VaultedPaymentMethodSelectedListener`  
  * Add `BottomSheetState`
  * Add `DropInEventType`
  * Add `DropInViewModel`
  * Add `SupportedPaymentMethodsViewHolder`
* Exceptions
  * Add `PaymentMethodDeleteException`
* Breaking Changes
  * Dependencies
    * Bump braintree_android module dependency versions to `4.4.1`
  * Package Structure
    * Flatten package structure and move all classes to `com.braintreepayments.api` package
  * DropInRequest
    * Remove `clientToken`, `tokenizationKey`, and `authorization` from `DropInRequest` in favor of instantiating `DropInClient` with authorization
    * Remove deprecated `amount` parameter from `DropInRequest`
    * Remove `intent` from `DropInRequest`
    * Remove builder pattern from `DropInRequest`
    * Update `DropInRequest` getter and setter methods to follow consistent naming for Kotlin synthesized properties
  * DropInResult
    * Remove `DropInResultListener`
    * Remove `DropInResult#fetchDropInResult()` 
    * Make `DropInResult` constructor package-private
  * PaymentMethodType
    * Rename `PaymentMethodType` to `DropInPaymentMethodType`
    * Change `DropInPaymentMethodType#getCardTypes()` parameter from `Set` to `List`
  * DropInActivity
    * Remove `ConfigurationListener`, `PaymentMethodNonceCreatedListener`, `PaymentMethodNonceUpdatedListener`, `PaymentMethodSelectedListener`, `BraintreeErrorListener`, `BraintreeCancelListener` from `DropInActivity`
    * Replace `DropInActivity.EXTRA_ERROR` with `DropInResult.EXTRA_ERROR`
    * Remove `BaseActivity`
    * Remove `onBackPressed`, `onBackgroundClicked` and `onVaultEditButtonClicked` methods
  * Fragment Architecture
    * Replace `VaultManagerActivity` with `VaultManagerFragment`
    * Replace `AddCardActivity` with `AddCardFragment` and `CardDetailsFragment`
  * Adapters
    * Make `SupportedPaymentMethodsAdapter` package-private
    * Make `VaultedPaymentMethodsAdapter` package-private
    * Make `VaultManagerPaymentMethodsAdapter` package-private
  * Listeners
    * Remove `AddPaymentUpdateListener`
    * Remove `AnimationFinishedListener`
  * CardViews
    * Remove `AddCardView`
    * Remove `EditCardView`
    * Remove `EnrollmentCardView`

**Note:** The credentials for integrating with 3DS have changed. If you are using 3DS please update the credentials in your app-level `build.gradle`

## 5.4.2

* Bump braintree_android version to 3.21.1

## 5.4.1

* Bump braintree_android version to 3.20.1

## 5.4.0

* Bump braintree_android version to 3.20.0

## 5.3.0

* Upgrade `targetSdkVersion` and `compileSdkVersion` to API 31
* Bump braintree_android version to 3.18.0

## 5.2.2

* Bump braintree_android version to 3.17.4

**Note:** The credentials for integrating with 3DS have changed. If you are using 3DS please update the credentials in your app-level `build.gradle` see [3DS Client Side Setup](https://developer.paypal.com/braintree/docs/guides/3d-secure/client-side#generate-a-client-token) 

## 5.2.1

* Bump card-form version to 5.1.1

## 5.2.0

* Update android-card-form version to 5.1.0 (fixes #212)
* Fix null pointer crash in `BaseActivity#shouldRequestThreeDSecureVerification` (fixes #207)
* Update Visa card icons

## 5.1.0

* Update Google Pay icon to meet updated [brand guidelines](https://developers.google.com/pay/api/android/guides/brand-guidelines#google-pay-logo-mark)
* Bump three-d-secure version to 3.15.0

## 5.0.2

* Fix issue where payment methods disabled on `DropInRequest` were displayed if previously vaulted (fixes #205)
* Bump braintree_android version to 3.15.0 (fixes #208)

## 5.0.1

* Bump braintree_android version to 3.14.2 (fixes #197)
* Upgrade Android Gradle Plugin to version 4.1.0

## 5.0.0

* Add `vaultVenmo` option to `DropInRequest`
* Bump braintree_android version to 3.14.1
* Bump `compileSdkVersion` and `targetSdkVersion` to API level 30
* Breaking Changes
  * Bump card-form version to 5.0.0 (removes support for CardIO, a no longer maintained framework)

## 4.6.0

* Bump braintree_android version to 3.11.1
* Bump card-form version to 4.3.0 (Updates Card icons)
* Update payment method icons (fixes issue where Google Pay icon did not meet new [brand guidelines](https://developers.google.com/pay/api/web/guides/brand-guidelines))
* Update `bt_add_card` string resource for french locales.
* Add 3DS support for non-network tokenized Google Pay cards

## 4.5.0

* Bump braintree_android version to 3.7.2

## 4.4.1

* Fix bug in `AddCardActivity#onError` that prevented passing error cases up to the appropriate listeners.

## 4.4.0

* Bump braintree_android version to 3.6.0

## 4.3.1

* Deprecate `amount` property on `DropInRequest`

## 4.3.0

* Bump braintree_android version to 3.4.1
* Add Support for 3DS 2.0
* Fix a bug with DropInActivity#onActivityResult (Thanks @xX7!)

## 4.2.0

* Add ability for merchant and/or customer to opt in/out of client side vaulting (card).

## 4.1.1

* Add `DropInRequest#disableCard` to disable Card payment method
* Fix Google Payment issue where Google Pay does not communicate back to BraintreeFragment

## 4.1.0

* Add Hiper and Hipercard detection and assets
  * Bump card-form to 4.1.0

## 4.0.0

* Bump minSdkVersion to 21
* Convert to AndroidX
* Removed Android Pay

## 3.7.1

* Upgrade braintree_android to 2.18.1 fixes Chrome Custom Tab integration when using Jetifier to use AndroidX

## 3.7.0

* Cardholder Name
  * Field for the Cardholder's name
  * Is disabled by default but can be required, or an optional field
* Upgrade card-form to 3.5.0
* Upgrade Android SDK to 28

## 3.6.1

* Vault Manager
  * Fix edit button default visibility

## 3.6.0

* Vault Manager
  * Allows for the deletion of vaulted payment methods

## 3.5.2

* Upgrade card-form to 3.4.1

## 3.5.1

* Upgrade card-form to 3.4.0

## 3.5.0

* Add support for `PayPalRequest` to customize the PayPal flow
  * Specifying an `amount` on the `PayPalRequest` will result in a One-Time payment

## 3.4.0

* Update spanish translation for bt_descriptor_unknown
* Upgrade Braintree to 2.13.1

## 3.3.0

* Enable input masking in AddCardActivity
* Update target SDK versions

## 3.2.1

* Upgrade Braintree to 2.10.0
* Restore the configuration after activity resumed (fixes [#181](https://github.com/braintree/braintree_android/issues/181))

## 3.2.0

* Add Google Pay support
* Update vaulted Maestro logos
* Update vaulted Mastercard logos
* Upgrade Braintree to 2.8.1
* Fix card number errors not being displayed
* Upgrade card-form to 3.1.1

## 3.1.0

* Fix missing French translations (fixes [#35](https://github.com/braintree/braintree-android-drop-in/issues/35))
* Stop using dependency ranges (https://github.com/braintree/android-card-form/pull/29)
* Prevent users from getting stuck when canceling 3D Secure (fixes [#41](https://github.com/braintree/braintree-android-drop-in/issues/41))
* Run 3D Secure verifications for vaulted credit cards (fixes [#41](https://github.com/braintree/braintree-android-drop-in/issues/41))
* Update compile and target SDK versions to 26
  * Any support library dependencies must now be 26.0.0 or newer
* Fix incorrect error message for empty client tokens or tokenization keys
* Upgrade card-form to 3.1.0
* Upgrade Braintree to 2.6.2

## 3.0.8

* Prevent dependency resolution of alpha major versions of support libraries (fixes [#28](https://github.com/braintree/braintree-android-drop-in/issues/28))

## 3.0.7

* Upgrade android-card-form to 3.0.4
* Upgrade Braintree to 2.4.3
* Handle `GoogleApiClientException`s instead of exiting `Activity` (fixes [#22](https://github.com/braintree/braintree-android-drop-in/issues/22))
* Respect `DropInRequest` payment method overrides (fixes [#27](https://github.com/braintree/braintree-android-drop-in/issues/27))

## 3.0.6

* Upgrade Braintree to 2.4.2

## 3.0.5

* Filter Android Pay from the list of vaulted payment methods (fixes [#15](https://github.com/braintree/braintree-android-drop-in/issues/15))
* Always return a serialized exception in `Activity#onActivityResult` when there is an error
* Upgrade Braintree to 2.4.0
* Increase `minSdkVersion` to 16
  * API 16 is the first version of Android that supports TLSv1.2. For more information on Braintree's upgrade to TLSv1.2 see [the blog post](https://www.braintreepayments.com/blog/updating-your-production-environment-to-support-tlsv1-2/).

## 3.0.4

* Update `android-card-form` to 3.0.3

## 3.0.3

* Fix an issue where Drop-in would not repect the `mAndroidPayEnabled` flag (thanks @bblackbelt)

## 3.0.2

* Fix missing security code name in CVV string. (fixes [#5](https://github.com/braintree/braintree-android-drop-in/issues/5))

## 3.0.1

* Update compile and target SDK versions to 25
* Improve UnionPay enrollment and error handling
* Update translations
  * Drop-in is now available in 23 languages: ar, da, de, en, es, fr-rCA, fr, in, it, iw,
      ja, ko, nb, nl, pl, pt, ru, sv, th, tr, zh-rCN, zh-rHK, zh-rTW.
* Upgrade android-card-form to 3.0.2
* Improve layout for right to left languages
* Add option to perform a 3D Secure verification when adding a card
* Upgrade Braintree to 2.3.11

## 3.0.0

* All new UI and integration for Drop-In
  * New assets
  * New bottom sheet UI
* Greater separation between payment methods and cards UI
* Fetch a customer's payment method without showing UI
* Added UnionPay support to Drop-In
* Drop-In no longer uses any internal methods in braintree_android

## 2.3.8

* Upgrade android-card-form to 2.3.2
* Upgrade Braintree 2.3.9
* Display card type when displaying Android Pay cards

## 2.3.7

* Update exception message when Android Manifest setup is invalid
* Fix unclosed `InputStream` (fixes [#115](https://github.com/braintree/braintree_android/issues/115))
* Post exception to error listener instead of throwing `IllegalStateException` when `BraintreeFragment` is not attached to an `Activity`
* Restore url when `BraintreeFragment` is recreated (fixes [#117](https://github.com/braintree/braintree_android/issues/117))
* Upgrade gradle build tools to 2.1.3
* Parse and return errors when Android Pay tokenization fails
* Add support for changing the backing card for Android Pay in Drop-In
* Call configuration callback whenever a new Activity is attached to `BraintreeFragment`

## 2.3.6

* Allow vaulting of Venmo accounts. See `Venmo#authorizeAccount`.
* Remove Venmo whitelist check
* Fix `BraintreeCancelListener#onCancel` being invoked twice for PayPal cancellations (fixes [#112](https://github.com/braintree/braintree_android/issues/112))

## 2.3.5

* Change `UnionPayCallback` to include `smsCodeRequired`
* Change `UnionPayCapabilities#isUnionPayEnrollmentRequired` to `UnionPayCapabilities#isSupported`
* Upgrade Google Play Services to [9.0.0,10.0.0)
* Upgrade support annotations to [24.0.0,25.0.0)
* Upgrade build tools to 24.0.0
* Update compile and target API versions to 24
* Fix `NullPointerException` in `AnalyticsIntentService`

## 2.3.4

* Prevent invalid schemes from being used for browser switching (Packages containing underscores would generate invalid schemes)
* Fix `NoClassDefFoundError` in `DataCollector`
* Fix `NullPointerException` in `BraintreeFragment`

## 2.3.3

* Add PayPal Checkout intent option (authorize or sale). See `PayPalRequest#intent`
* Update UnionPay support in demo app custom integration
* Update `android-card-form` to 2.3.1
* Fix `NullPointerException` in `AddPaymentMethodViewController` (fixes [#100](https://github.com/braintree/braintree_android/issues/100))
* Fix `IllegalStateException` when creating a `BraintreeFragment` (fixes [#104](https://github.com/braintree/braintree_android/issues/104))
* Fix `NullPointerException` when `BraintreeFragment` is not attached to an `Activity` (fixes [#105](https://github.com/braintree/braintree_android/issues/105))

## 2.3.2

* Fix `NullPointerException` when handling a PayPal response (fixes [#101](https://github.com/braintree/braintree_android/issues/101))

## 2.3.1

* Fix `NullPointerException`s in `BraintreeFragment` when not attached to an `Activity`
* Fix Chrome Custom Tabs Intent flags interfering with browser switch
* Add new `DataCollector#collectDeviceData` methods that use a callback; deprecate synchronous methods
* Reduce size of assets in Drop-In

## 2.3.0

* UnionPay Beta *Please note*: this API is in beta and subject to change
* Add support for fetching a customer's payment methods
* Return a `RateLimitException` when a merchant account is being rate limited

## 2.2.5

* Fixes
  * Update BraintreeHttpClient to support UTF-8 encoding (fixes [#85](https://github.com/braintree/braintree_android/issues/85))

## 2.2.4

* Update PayPalDataCollector to 3.1.1
* Fixes
  * Update device collector to 2.6.1 (fixes [#87](https://github.com/braintree/braintree_android/issues/87))
  * Fix crash when `BraintreeFragment` has not been attached to an `Activity`
* Features
  * Add `PaymentRequest#defaultFirst` option
  * Add support for Chrome Custom tabs when browser switching

## 2.2.3

* Fixes
  * Fix incorrect `groupId` of dependencies in pom file for 2.2.2

## 2.2.2

:rotating_light: The `groupId`s in this version's pom files are incorrect and dependencies will not resolve. Do not use. :rotating_light:

* Update `PaymentButton` styling when PayPal is the only visible option
* Features
  * Add client side overrides for payment methods in Drop-in and `PaymentButton` to `PaymentRequest`
  * Add support for non-USD currencies and non-US shipping addresses in Android Pay
  * Return email, billing address and shipping address as part of an `AndroidPayCardNonce` from Drop-in
* Fixes
  * Fix back button not doing anything in Drop-in after an Android Pay error is returned
  * Deprecate `DataCollector#collectDeviceData` and add new signature to prevent a NullPointerException when using a fragment that is not attached to an `Activity`

## 2.2.1

* Fixes
  * Fix support annotations being bundled in PayPalDataCollector jar

## 2.2.0

* Open source PayPal SDK
* Deprecate `PayPalOneTouchActivity` and remove from Android manifest
* Add Travis CI build
* Improve errors and manifest validation
* Features
  * Add `CardBuilder#cardholderName`
  * Add `PayPalRequest#billingAgreementDescription`
* Fixes
  * Fix back button not working in Drop-in after adding a payment method
  * Fix failure to return a payment method nonce after browser switch when the fragment was recreated.

## 2.1.2

* Update Google Play Services Wallet to 8.4.0
* Use `ENVIRONMENT_TEST` for Android Pay requests in sandbox
* Add `AndroidPay#isReadyToPay` method

## 2.1.1

* Demo app upgrades
* Update PayPal SDK to 2.4.3 (fixes [#67](https://github.com/braintree/braintree_android/issues/67))
* Update android-card-form to 2.1.1
* Update gradle to 2.8
* Update build tools to 23.0.2
* Features
  * Add support for fraud data collection in Drop-in
* Fixes
  * Add rule to suppress ProGuard warnings
  * Fix Drop-in crash
  * Fix NPE when there is no active network (fixes [#77](https://github.com/braintree/braintree_android/issues/77))

## 2.1.0

* Pay with Venmo
* `PaymentButton#newInstance` now accepts a container id to add `PaymentButton` to that container
* Android Pay assets
* Fixes
  * Add `onInflate` method for Android versions < 23
  * PayPal cancel events (fixes [#63](https://github.com/braintree/braintree_android/issues/63))

## 2.0.1

* Make support annotations an optional dependency
* Cache configuration to prevent unnecessary network requests
* Fixes
  * Fix BraintreeDataCollector as an optional dependency
  * Fix `PaymentRequest` crash when Google Play Services is not present

## 2.0.0

* Increase `minSdkVersion` to 15 (see [Platform Versions](http://developer.android.com/about/dashboards/index.html#Platform) for the current distribution of Android versions)
* Remove Gson dependency
* Replace `Braintree` class with headless `BraintreeFragment`
  * Move methods for creating payment methods from central `Braintree` class to their own classes e.g. `PayPal#authorizeAccount`, `Card#tokenize`
* Add support for Tokenization Keys in addition to Client Tokens
* Rename PaymentMethod to PaymentMethodNonce
* Rename BraintreeData module to BraintreeDataCollector
* Update PayPal
  * Remove [PayPal Android SDK](https://github.com/paypal/PayPal-Android-SDK) dependency
  * Replace in-app log in with browser based log in
  * Add support for PayPal billing agreements and one-time payments
* Convert `PaymentButton` class from a view to a fragment
* Create `PaymentRequest` class for specifying options in Drop-in and the `PaymentButton`
* Remove Venmo One Touch. To join the beta for Pay with Venmo, contact [Braintree Support](mailto:support@braintreepayments.com)
* Remove Coinbase
