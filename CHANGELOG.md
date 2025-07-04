# Changelog

## 4.29.0

- Add Session Id to Customer Recommendations Payload

## 4.28.0

- Add `account_information_inquiry` to
  - `CreditCardVerification#create`
  - `PaymentMethod#create` and `PaymentMethod#update`
  - `CreditCard#create` and `CreditCard#update`
- Enhancements to PayPal customer recommendations
  - Create a session and get recommendations in one call
  - Hash customer email and phone number
- Add `business`, `consumer`, `corporate`, and `purchase` from the bin data to credit card responses

## 4.27.0

- Remove marketplace features
- Add support for capturing payment facilitator and sub-merchant details with transactions 

## 4.26.0

- Add `prepaid_reloadable` from the bin data to credit card responses
- Add support for `PayPalPaymentResource` requests

## 4.25.0

- Add support for creating and updating PayPal customer session
- Add support for getting PayPal customer recommendations

## 4.24.0 

- Add recipient/contact info: `recipient_email`and `recipient_phone` to `Transaction` 

## 4.23.0

- Add `fail_on_duplicate_payment_method_for_customer` option to 
  - `ClientToken`
  - `PaymentMethod`
  - `CreditCard`
- Add `blik_aliases` to LocalPaymentCompleted webhook
- Deprecate `samsung_pay_card`
- Updated expiring pinned vendor SSL certificates

## 4.22.0

- Add `payer_name`, `bic` and `iban_last_chars` to LocalPaymentCompleted webhook
- Add `edit_paypal_vault_id` to PayPalAccount
- Removes redundant integration test for provision_raw_apple_pay
- Add `ani_first_name_response_code` and `ani_last_name_response_code` to CreditCardVerification
- Add `shipping_tax_amount` to Tranaction

## 4.21.0

- Add `foreign_retailer` to Transaction
- Add `international_phone` to `Address` and `Customer`
- Add `funding_source_description` to PayPalAccount
- Add missing `GooglePayCard` error code
- Add `REFUND_FAILED` to Webhook Notification
- Add `final_capture` to Transaction `_submit_for_partial_settlement_signature`
- Deprecate `paypal_tracking_id` in favor of `paypal_tracker_id` in `package_details.rb`

## 4.20.0

- Deprecate `credit` method in `credit_card` and `credit_card_gateway`
- Deprecate `sale` method in `credit_card` and `credit_card_gateway`
- Add `domains` parameter support to `ClientToken::generate`

## 4.19.0

- Add `UnderReview` status to `Dispute`
- Add `DisputeUnderReview` webhook to `WebhookNotification`
- Cleanup useless assignments in XML::Parser, Util, HTTP, Disbursement, and Configuration classes
- Fix issue where advanced searches using `between` were not correctly evaluating values
  larger than the minimum

## 4.18.0

- Add `process_debit_as_credit` to `credit_card` field in `options` field during Transaction create
- Add `package_tracking` method to `transaction_gateway` to make request to add tracking information to transactions
- Add `packages` to Transaction object
- Add `image_url`,`upc_code`, and `upc_type` to `LineItems` in `transaction_gateway`

## 4.17.0

- Add `PickupInStore` to `ShippingMethod` enum
- Add `external_vault` and `risk_data` to `CreditCardVerification` create request

## 4.16.0

- Add `meta_checkout_card` and `meta_checkout_token` payment methods 
- Add `meta_checkout_card_details` and `meta_checkout_token_details` to Transaction
- Add `industry_data` to `Transaction.submit_for_settlement` options
- Add `dateOfBirth` and `countryCode` parameters to `Transaction.sale.industry.data`
- Add `billing_address` and `shipping_address` to `VenmoProfileData`
- Add `additional_processor_response` to `UsBankAccountVerification`
- Add `verification_add_ons` to `PaymentMethod` create options for `ACH NetworkCheck`
- Add `Maestro` to `DebitNetwork` enum

## 4.15.0

- Add `retry_ids`, `retried_transaction_id`, and `debit_network` to `Transaction`
- Add `evidence_submittable` to Dispute
- Add `implicitly_vaulted_payment_method_token` and `implicitly_vaulted_payment_method_global_id` to `LocalPaymentDetails`
- Add `merchant_token_identifier` and `source_card_last4` to ApplePayCard and ApplePayDetails response objects
- Add `debit_network` to `TransactionSearch`
- Add `DebitNetwork` enum to `CreditCard`
- Add `SubscriptionBillingSkipped` webhook notification support
- Deprecate `three_d_secure_token` in favor of `three_d_secure_authentication_id`
- Deprecate `venmo_sdk_session`, `venmo_sdk_payment_method_code`, and `venmo_sdk?`

## 4.14.0

- Add `payment_receipt` object to `Transaction`
- Add `global_id` string to `UsBankAccountDetails`

## 4.13.0

- Add `retry_ids` array to `Transaction`
- Add `retried_transaction_id` string to `Transaction`
- Add `merchant_token_identifier` and `source_card_last4` to ApplePayCard and ApplePayDetails response objects
- Add `processing_overrides` to `Transaction.sale` options
- Add `arrival_date` and `ticket_issuer_address` to `industry` object in `Transaction` and add `industry` to `Transaction.submit_for_settlement`

## 4.12.0

- Add `merchant_advice_code` and `merchant_advice_code_text` to Transaction object

## 4.11.0

- Add `intended_transaction_source` to `CreditCardVerificationGateway`
- Add `payment_method_nonce` to `CreditCardVerificationGateway`
- Add `three_d_secure_authentication_id` to `CreditCardVerificationGateway`
- Add `three_d_secure_pass_thru` to `CreditCardVerificationGateway`
- Add `network_tokenization_attributes` parameter to `Transaction.sale`
- Add `network_token_details` to Transaction.sale response
- Add `is_network_tokenized` to `CreditCardDetails`
- Add subscriptions to `SepaDirectDebitAccount`

## 4.10.0

- Add `billing_address` attribute reader to `ApplePayCard`
- Add `pre_dispute_program` to `Dispute` and `DisputeSearch`
- Add `AutoAccepted` status to `Dispute`
- Add `DisputeAutoAccepted` webhook to `WebhookNotification`
- Add `ExcessiveRetry` to `GatewayRejectionReason`
- Add `SEPADirectDebitAccount` payment method
- Add `sepa_direct_debit_return_code` to `Transaction`
- Add `sepa_direct_debit_account_details` to `Transaction`
- Add `sepa_direct_debit_account_nonce_details` to `PaymentMethodNonceDetails`
- Add `SEPA_DIRECT_DEBIT_ACCOUNT` to `PaymentInstrumentType`
- Add `sepa_debit_paypal_v2_order_id` to `TransactionSearch`
- Add `sepa_direct_debit_accounts` to `Customer`
- Add SEPA Direct Debit specific error codes

## 4.9.0

- Add `cardholder_name` attribute reader to `ApplePayCard` (Thanks @AxelTheGerman)
- Deprecate `chargeback_protection_level` and add `protection_level` to `Dispute` and `DisputeSearch`

## 4.8.0

- Add `ach_return_responses` to `Transaction` for search results that search for transaction that have ach return response related data.
- Add `ach_return_responses_created_at` range field to to `TransactionSearch`
- Add `reason_code` to TransactionSearch to search for reason codes on transaction that have ach return responses associated with them.
- Add 'ExchangeRateQuoteAPI'
- Add LiabilityShift class and `liability_shift` field to RiskData
- Replace generic errors with api_error_response

## 4.7.0

- Add `AchReturnCode` to transaction object
- Add `retried` boolean to `Transaction`

## 4.6.0

- Add `PaymentMethodCustomerDataUpdated` webhook notification support

## 4.5.0

- Add plan create/update/find API endpoint
- Add support for `TransactionReview` webhook notification

## 4.4.0

- Sanitize encrypted_card_data logs
- Add `LocalPaymentExpired` and `LocalPaymentFunded` webhook notification support

## 4.3.0

- Add a log message to the `ArgumentError` at `TransactionGateway.find`
- Add `exchange_rate_quote_id` to `Transaction.create`
- Add error code `ExchangeRateQuoteIdTooLong` to `Transaction`
- Add the following fields to `ApplePayCard` and `GooglePayCard`:
  - `commercial`
  - `debit`
  - `durbin_regulated`
  - `healthcare`
  - `payroll`
  - `prepaid`
  - `product_id`
  - `country_of_issuance`
  - `issuing_bank`
- Add the following fields to `PayPalDetails`:
  - `tax_id`
  - `tax_id_type`

## 4.2.0

- Add `default?` to `PaymentMethodNonce` (thanks @klouvas)
- Add error code `TaxAmountIsRequiredForAibSwedish` for attribute `tax_amount` in `transaction` key for AIB:Domestic Transactions in Sweden

## 4.1.0

- Add `payment_reader_card_details` parameter to `Transaction.sale`
- Add webhook sample for `GrantedPaymentMethodRevoked`
- Add `skip_advanced_fraud_checking` to:
  - `Customer#create` and `Customer#update`
  - `PaymentMethod#create` and `PaymentMethod#update`
  - `CreditCard#create` and `CreditCard#update`
- Include `rexml` in Gemspec (fixes #214)
- Fix incorrect error code constants (fixes #213)
  - `PaymentMethodNonceConsumed` is now `93107`
  - `CannotForwardPaymentMethodType` is now `93106`

## 4.0.0

- Breaking Changes
  - Update gemspec to require ruby >= 2.6.0
  - Remove `ExternalVault::CardTypeIsInvalid` error code
  - Remove `RiskData::CustomerBrowserIsTooLong` error code
  - Remove `paypal_vault_without_upgrade` parameter from `PaymentMethod#create`
  - Add `PaymentMethodNonceDetails` and `PaymentMethodNonceDetailsPayerInfo`
    - `PaymentMethodNonce#details` is now an instance of `PaymentMethodNonceDetails` rather than a hash
    - `PaymentMethodNonceDetails#payer_info` is now an instance of `PaymentMethodNonceDetailsPayerInfo` rather than a hash
- Add `phone_number` to `Address`
- Add `paypal_messages` to `Dispute`
- Add `tax_identifiers` parameter to `Customer.create` and `Customer.update`
- Add `chargeback_protection_level` into dispute search
- Make libxml-ruby an optional dependency instead of required (addresses JRuby incompatibility issues raised in #203 and #205)

## 3.4.0

- Add `local_payment_reversed` webhook notification
- Add `Transaction.adjust_authorization` method to support for multiple authorizations for a single transaction
- Add `merchant_account_id` parameter to `Transaction#refund`
- Add `store_id` and `store_ids` parameters to `Transaction#search`
- Add support for `ActiveSupport::TimeWithZone` when generating XML (thanks @Tonkpils!)

## 3.3.0

- Add `decision_reasons` and `transaction_risk_score` fields to `RiskData`
- Add `acs_transaction_id`, `pares_status`, `three_d_secure_transaction_id`, `lookup`, and `authentication` to `ThreeDSecureInfo`

## 3.2.0

- Add SCA exemption to Transaction sale
- Add Installment support to Transaction sale
  - Add `installment_count` to `Transaction`
  - Add new `Installment` and `Installment::Adjustment` classes to `Transaction`
- Add `verification_currency_iso_code` parameter to `Customer.create`, `PaymentMethod.create`, `CreditCard.create`, `Customer.update`, `PaymentMethod.update`, and `CreditCard.update`
- Add `currency_iso_code` parameter to `Transaction.sale`
- Add validation errors
  - `CreditCard::CurrencyCodeNotSupportedByMerchantAccount`
  - `Transaction::CurrencyCodeNotSupportedByMerchantAccount`
- Allows `ResourceCollection#first` to receive one argument and return that argument number of items(Thanks @regismesquita)

## 3.1.0

- Add `acquirer_reference_number` to `Transaction`
- Add `billing_agreement_id` to `PayPalDetails`
- Update `BinData` class to correctly execute the `inspect` method.(Thanks @kinduff)

## 3.0.1

- Add `CreditCardVerification::GatewayRejectionReason`
- Memory improvements related to XML parsing (addresses #159)
- Breaking changes:
  - Remove support for Transparent Redirect, Coinbase, iDEAL, Amex Express Checkout and Masterpass
  - Rename `DownForMaintenanceError` to `ServiceUnavailableError`
  - Update `Transaction.search` to raise an `UnexpectedError` if the search yields unexpected results
  - Add `GatewayTimeoutError` and `RequestTimeoutError`
  - Remove `ForgedQueryString` error
  - Remove error codes:
    - EuropeBankAccount.IBANIsRequired
    - EuropeBankAccount.BICIsRequired
    - EuropeBankAccount.AccountHolderNameIsRequired
    - SEPAMandate.AccountHolderNameIsRequired
    - SEPAMandate.BICIsRequired
    - SEPAMandate.IBANIsRequired
    - SEPAMandate.TypeIsRequired
    - SEPAMandate.IBANInvalidCharacter
    - SEPAMandate.BICInvalidCharacter
    - SEPAMandate.BICLengthIsInvalid
    - SEPAMandate.BICUnsupportedCountry
    - SEPAMandate.IBANUnsupportedCountry
    - SEPAMandate.IBANInvalidFormat
    - SEPAMandate.LocaleIsUnsupported
    - SEPAMandate.BillingAddressIsInvalid
    - SEPAMandate.TypeIsInvalid
    - Transaction.AmountDoesNotMatchIdealPaymentAmount
    - Transaction.IdealPaymentNotComplete
    - Transaction.IdealPaymentsCannotBeVaulted
    - Transaction.MerchantAccountDoesNotMatchIdealPaymentMerchantAccount
    - Transaction.OrderIdDoesNotMatchIdealPaymentOrderId
    - Transaction.OrderIdIsRequiredWithIdealPayment
    - TransactionLineItem.DiscountAmountMustBeGreaterThanZero
    - TransactionLineItem.UnitTaxAmountMustBeGreaterThanZero
  - Remove deprecated methods:
    - Address#delete
    - Address#update and Address#update!
    - CreditCard.grant
    - CreditCard#credit and CreditCard#credit!
    - CreditCard#delete
    - CreditCard#sale and CreditCard#sale!
    - CreditCard#update and CreditCard#update!
    - CreditCardGateway#grant
    - Customer#default_credit_card
    - Customer#sale and Customer#sale!
    - Customer#update and Customer#update!
    - Dispute#forwarded_comments
    - Subscription#next_bill_amount
    - Transaction#refund
    - Transaction#refund_id
    - Transaction#submit_for_settlement and Transaction#submit_for_settlement!
    - Transaction#void and Transaction#void!
  - Remove unused WebhookNotification::Kind::GrantedPaymentInstrumentUpdate
  - Rename all Android Pay classes and methods to Google Pay
  - Rename Dispute::HistoryEvent to Dispute::StatusHistory
  - Update the following methods to return `Date`s instead of `Strings` (fixes #161):
    - DisbursementDetails#disbursement_date
    - StatusHistory#disbursement_date
    - StatusHistory#effective_date
    - Subscription#billing_period_end_date
    - Subscription#billing_period_start_date
    - Subscription#first_billing_date
    - Subscription#next_billing_date
    - Subscription#paid_through_date
    - SubscriptionDetails#billing_period_end_date
    - SubscriptionDetails#billing_period_start_date
  - Bump API version to support declined refund objects
  - Remove deprecated parameters:
    - `device_session_id` from CreditCard#create, Transaction#sale, PaymentMethod#create, and Customer#create
    - `fraud_merchant_id` from CreditCard#create, Transaction#sale, PaymentMethod#create, and Customer#create
    - `recurring` from Transaction#sale
  - Update builder dependency to >= 3.2.4
  - Update libxml-ruby dependency to >= 3.2.0
  - Update gemspec to require ruby >= 2.5.0

## 3.0.0

This version has been yanked from rubygems, do not use.

## 2.104.1

- Update `LocalPaymentCompleted` webhook to handle no transaction being created for unbranded local payment methods

## 2.104.0

- Deprecate Masterpass and American Express Checkout payment methods.
- Add `installment_count` accessor to `dispute.transaction` on dispute webhooks
- Add `implicitly_vaulted_payment_method_token` and `implicitly_vaulted_payment_method_global_id` to `paypal_details`

## 2.103.0

- Add `RiskThreshold` to gateway rejection reasons
- Add `network_transaction_id` to `CreditCardVerification`
- Add `product_sku` to `Transaction`
- Add `phone_number` and `shipping_method` to `AddressDetails`
- Add `customer_device_id`, `customer_location_zip`, and `customer_tenure` to `RiskData`
- Add validation errors:
  - `Transaction::ProductSkuIsInvalid`
  - `Transaction::ShippingMethodIsInvalid`
  - `Transaction::ShippingPhoneNumberIsInvalid`
  - `Transaction::BillingPhoneNumberIsInvalid`
  - `RiskData::CustomerBrowserIsTooLong`
  - `RiskData::CustomerDeviceIdIsTooLong`
  - `RiskData::CustomerLocationZipInvalidCharacters`
  - `RiskData::CustomerLocationZipIsInvalid`
  - `RiskData::CustomerLocationZipIsTooLong`
  - `RiskData::CustomerTenureIsTooLong`
- Add `processed_with_network_token` to `Transaction`
- Add `is_network_tokenized` to `CreditCard`
- Add `created_at` accessor to `dispute.transaction` on dispute webhooks (closes #200)

## 2.102.0

- Add `threeDSecurePassThru` parameters to `Customer.create`, `PaymentMethod.create`, `CreditCard.create`, `Customer.update`, `PaymentMethod.update`, and `CreditCard.update`
- Add `recurring_customer_consent`and `recurring_max_amount` options to `authentication_insight`to payment method nonce create
- Add ThreeDSecure test payment method nonces
- Add test `AuthenticationId`s
- Add `DisputeAccepted`, `DisputeDisputed`, and `DisputeExpired` webhook constants
- Add `Authentication Insight` to payment method nonce create
- Add `FileIsEmpty` error to `DocumentUpload`
- Add `retrieval_reference_number` to `Transaction`

## 2.101.0

- Add `RefundAuthHardDeclined` and `RefundAuthSoftDeclined` to validation errors
- Add `is_network_tokenized?` to android_pay_card and android_pay_details
- Add handling for `gzip` encoding to `graphql_client`
- Add Graphql ID to `CreditCardVerification`, `Customer`, `Dispute`, and `Transaction`
- Add `three_d_secure_authentication_id` to `ThreeDSecureInfo`
- Add `three_d_secure_authentication_id` support to transaction
- Add level 2 processing options `purchase_order_number`, `tax_amount`, and `tax_exempt` to Transaction submit_for_settlement
- Add level 3 processing options `shipping_amount`, `discount_amount`, `ships_from_postal_code`, and `line_items` to Transaction submit_for_settlement

## 2.100.0

- Add `ProcessorDoesNotSupportMotoForCardType` to validation errors
- Add `bin` to `apple_pay_details` and `android_pay_details`

## 2.99.0

- Add `processor_comments` to `Dispute`
- Deprecate `forwarded_comments` on `Disputes`

## 2.98.0

- Add `network_response_code` and `network_response_text` to transactions and verifications
- Add `PayPalHereDetails`
- Add `three_d_secure_info` to credit_card_verification
- Add `xid`, `cavv`, `eciFlag`, `dsTransactionId`, and `threeDSecureVersion` to `ThreeDSecureInfo`
- Add `graphql_client` to `Braintree::Gateway` class
- Add `AmountNotSupportedByProcessor` to validation error

## 2.97.0

- Add `capture_id` to local_payment_details
- Add `refund_id` to local_payment_details
- Add `debug_id` to local_payment_details
- Add `transaction_fee_amount` to local_payment_details
- Add `transaction_fee_currency_iso_code` to local_payment_details
- Add `refund_from_transaction_fee_amount` to local_payment_details
- Add `refund_from_transaction_fee_currency_iso_code` to local_payment_details
- Add `three_d_secure_version`, `authentication_response`, `directory_response`, `cavv_algorithm` and `ds_transaction_id` to 3DS pass thru fields
- Add verification_account_type support for credit_card create/update and customer create/update
- Add `room_tax` field to transactions
- Add `no_show` field to transactions
- Add `advanced_deposit` field to transactions
- Add `fire_safe` field to transactions
- Add `property_phone` field to transactions
- Add `additional_charges` field to transactions
- Add `payer_info` to payment_method_nonce details
- Add `PostalCodeIsRequiredForCardBrandAndProcessor` to validation errors

## 2.96.0

- Add `prepaid` field to android_pay_card
- Add `healthcare` field to android_pay_card
- Add `debit` field to android_pay_card
- Add `durbin_regulated` field to android_pay_card
- Add `commercial` field to android_pay_card
- Add `payroll` field to android_pay_card
- Add `issuing_bank` field to android_pay_card
- Add `country_of_issuance` field to android_pay_card
- Add `product_id` field to android_pay_card
- Add `global_id` field to android_pay_card
- Add `prepaid` field to apple_pay_card
- Add `healthcare` field to apple_pay_card
- Add `debit` field to apple_pay_card
- Add `durbin_regulated` field to apple_pay_card
- Add `commercial` field to apple_pay_card
- Add `payroll` field to apple_pay_card
- Add `issuing_bank` field to apple_pay_card
- Add `country_of_issuance` field to apple_pay_card
- Add `product_id` field to apple_pay_card
- Add `bin` field to apple_pay_card
- Add `global_id` field to apple_pay_card
- Add `refund_from_transaction_fee_amount` field to paypal_details
- Add `refund_from_transaction_fee_currency_iso_code` field to paypal_details
- Add `revoked_at` field to paypal_account
- Add support for `PaymentMethodRevokedByCustomer` webhook
- Add `payment_method_nonce` field to `LocalPaymentCompleted` webhook
- Add `transaction` field to `LocalPaymentCompleted` webhook
- Add `local_payment_detail` field to transactions
- Add `TokenIssuance` gateway rejection reason enum

## 2.95.0

- Deprecate `GrantedPaymentInstrumentUpdate` and add `GrantorUpdatedGrantedPaymentMethod` and `RecipientUpdatedGrantedPaymentMethod`
- Add account_type support for transaction sale, verification, and payment_method create/update

## 2.94.0

- Add `bin` field to `payment_method_nonce_details`
- Add Error indicating pdf uploads too long for dispute evidence.
- Add `GrantedPaymentMethodRevoked` webhook response objects
- Update BigDecimal#New calls to un-deprecated Kernel#BigDecimal calls
  - Thank you @john-denisov and @jfiander!

## 2.93.0

- Allow PayPal payment ID and payer ID to be passed during transaction create
- Add `travel_flight` support to industry-specific data
- Add `fraud_service_provider` field to `risk_data`

## 2.92.0

- Add `processor_response_type` to `Transaction`, `AuthorizationAdjustment`, and `CreditCardVerification`.
- Add `authorization_expires_at` to `Transaction`

## 2.91.0

- Add local payment webhook support
- Add subscription charged unsuccessfully sample webhook to webhook testing gateway
- Fix issue where environment was not automatically converted from a string to a symbol (#148, #164)
- Fix issue where logger could not be set on gateway instance
- Fix dispute results in transactions not showing the correct status sometimes
- Whitelist usage of `external_vault` in transaction create.
- Visa transactions will now contain a `network_transaction_id` in the response

## 2.90.0

- Add `processor_response_code` and `processor_response_text` to authorization adjustments subfield in transaction response.
- Stop restricting `transaction_source` values for Disputes search, allow searching by OAuth Application client_id
- Add support for Samsung Pay

## 2.89.0

- Warn when instantiating a `Braintree::Gateway` with mixed environments
- Allow payee ID to be passed in options params for transaction create
- Add `merchant_id` to `ConnectedMerchantStatusTransitioned` and `ConnectedMerchantPayPalStatusChanged` Auth webhooks

## 2.88.0

- Add support for Micro Transfer ACH verifications
- Add `image_url` and `token` attributes to `AndroidPayDetails` and `ApplePayDetails`

## 2.87.0

- Add Dispute error ValidEvidenceRequiredToFinalize

## 2.86.0

- Remove `sepa_mandate_type` and `sepa_mandate_acceptance_location` params from `ClientTokenGateway`
- Add `payer_id` accessor in `PayPalAccount`
- Add support for VCR compelling evidence dispute representment

## 2.85.0

- Add support for `oauth_access_revocation` on `WebhookNotification`s
- Add support for US Bank Account verifications via `PaymentMethod#create`, `PaymentMethod#update`, and `Transaction#create`
- Add support for US Bank Account verification search

## 2.84.0

- Add support for `address.create!` to gateway instance
- Add support for `address.update!` to gateway instance
- Add support for `credit_card.create!` to gateway instance
- Add support for `customer.create!` to gateway instance
- Add support for `customer.update!` to gateway instance
- Add support for `document_upload.create!` to gateway instance
- Add support for `merchant_account.create!` to gateway instance
- Add support for `merchant_account.update!` to gateway instance
- Add support for `payment_method.create!` to gateway instance
- Add support for `payment_method.update!` to gateway instance
- Add support for `payment_method_nonce.create!` to gateway instance
- Add support for `subscription.cancel!` to gateway instance
- Add support for `subscription.create!` to gateway instance
- Add support for `subscription.update!` to gateway instance
- Add support for `subscription.retry_charge` to gateway instance
- Add support for `transaction.cancel_release!` to gateway instance
- Add support for `transaction.hold_in_escrow!` to gateway instance
- Add support for `transaction.clone_transaction!` to gateway instance
- Add support for `transaction.credit!` to gateway instance
- Add support for `transaction.refund!` to gateway instance
- Add support for `transaction.release_from_escrow!` to gateway instance
- Add support for `transaction.sale!` to gateway instance
- Add support for `transaction.submit_for_settlement!` to gateway instance
- Add support for `transaction.submit_for_partial_settlement!` to gateway instance
- Add support for `transaction.void!` to gateway instance
- Add support for `profile_id` in Transaction#create options for VenmoAccounts
- Add support for `association_filter_id` in Customer#find
- Add support for `customer_id`, `disbursement_date` and `history_event_effective_date` in Dispute#search
- Update country names to have parity with documentation

## 2.83.0

- Add support for `tax_amount` field on transaction `line_items`
- Add support for `source_merchant_id` on webhooks
- Deprecated `DiscountAmountMustBeGreaterThanZero` error in favor of `DiscountAmountCannotBeNegative`.
- Deprecated `UnitTaxAmountMustBeGreaterThanZero` error in favor of `UnitTaxAmountCannotBeNegative`.
- Add `find_all` static method to `TransactionLineItem` class

## 2.82.0

- Add support for tagged evidence in DisputeGateway#add_text_evidence (Beta release)
- Update https certificate bundle

## 2.81.0

- Add support for line_items
- Update README to use instance methods

## 2.80.1

- Fix spec to expect PayPal transactions to move to settling rather than settled
- Fix permissions issue where SDK could not be loaded in some environments

## 2.80.0

- Add `bin_data` to Payment Method Nonce
- Add support for including level 3 summary fields to transaction create and transaction response

## 2.79.0

- Add `device_data_captured` field to `risk_data`
- Add submit_for_settlement to Braintree::Subscription.retry_charge
- Add `options` -> `paypal` -> `description` for creating and updating subscriptions
- Add `bin` to `ApplePayCard`
- Add support for upgrading a PayPal future payment refresh token to a billing agreement
- Fix spec to expect PayPal transaction to settle immediately after successful capture
- Add GrantedPaymentInstrumentUpdate webhook support
- Add `options` -> `paypal` -> `shipping` for creating & updating customers as well as creating payment methods
- Add ability to create a transaction from a shared nonce
- Add ruby 2.4 compatibility for the XML Generator (thanks @kinkade!)
- Add README note for supression of logs (thanks @badosu!)
- Allow `VenmoAccount` to be returned from `PaymentMethod.find` (thanks @NickMele!)

## 2.78.0

- Support `eci_indicator` for Transaction#sale with raw Apple Pay parameters

## 2.77.0

- Add `AuthorizationAdjustment` class and `authorization_adjustments` to Transaction
- Add document upload support
- Add Braintree::Dispute.find method
- Add Braintree::Dispute.search method
- Add Braintree::Dispute.accept method
- Add Braintree::Dispute.finalize method
- Add Braintree::Dispute.add_file_evidence method
- Add Braintree::Dispute.add_text_evidence method
- Add Braintree::Dispute.remove_evidence method
- Coinbase is no longer a supported payment method. `PaymentMethodNoLongerSupported` will be returned for Coinbase operations.
- Add Braintree::ApplePay for web domain registration
- Add facilitated details to Transaction if present

## 2.76.0

- Pass configured gateway to Merchant#\_new instead of using global gateway (thanks @cwalsh!)

## 2.75.0

- Add support for additional PayPal options when vaulting a PayPal Order

## 2.74.0

- Add Visa Checkout support
- Add ConnectedMerchantStatusTransitioned and ConnectedMerchantPayPalStatusChanged Auth webhooks
- Add new properties to `CreditCardVerification` and `Customer`

## 2.73.0

- Bugfix: Add `unique_number_identifier` to Transaction::CreditCardDetails
- Updates to specs

## 2.72.0

- Remove `account_description` field from +UsBankAccount+ and +UsBankAccountDetails+

## 2.71.0

- Allow optional configuration of SSL version
- Add functionality to list all merchant accounts for a merchant with `merchant_account.all`

## 2.70.0

- Bugfix: Update UsBank tests to use legal routing numbers
- Add option +skip_advanced_fraud_check+ for transaction flows
- Add IdealPayment class with +sale+ and +find+ methods
- Add payer_status accessor to paypal_details object

## 2.69.1

- Bugfix: Allow PaymentMethod.find(token) to return +UsBankAccount+

## 2.69.0

- Add +default?+ support for +UsBankAccount+
- Add +ach_mandate+ data to +UsBankAccount+ and +UsBankAccountDetails+

## 2.68.2

- Bugfix: allow Customer#payment_methods to return UsBankAccounts

## 2.68.1

- Fix compatibility with new gateway endpoint

## 2.68.0

- Add 'UsBankAccount' payment method

## 2.67.0

- Add 'created_at' to subscription search
- Expose 'plan_id' in subscription 'status_details'
- Add cannot clone marketplace transaction error
- Add FailOnDuplicatePaymentMethod to Customer update

## 2.66.0

- Add 'currency_iso_code' to subscription 'status_details'
- Expose credit card 'product_id'
- Add validation error for verifications with submerchants

## 2.65.0

- Allow authenticated proxies
- Add new constant for Venmo Account payment instrument type

## 2.64.0

- Add 'default_payment_method' option to Customer

## 2.63.0

- Add order_id to Refund
- Enabled 3DS pass thru support
- Expose IDs in resource collections
- Add 'success?' method to disbursement

## 2.62.0

- Add method of revoking OAuth access tokens.

## 2.61.1

- Fix compatibility in specs with Ruby 1.8.7

## 2.61.0

- Add transaction +UpdateDetails+
- Support for Too Many Requests response codes
- Add +default?+ method to MerchantAccount

## 2.60.0

- Allow Coinbase account to be updated
- Add support to pass currencies to merchant create
- Support multiple partial settlements
- Add IsInvalid error code for addresses

## 2.59.0

- Add support for third party Android Pay integrations

## 2.58.0

- Add AccountUpdaterDailyReport webhook parsing

## 2.57.0

- Add Verification#create
- Add options to +submit_for_settlement+ transaction flows
- Upgrade libxml-ruby version to 2.8.0
- Update https certificate bundle

## 2.56.0

- Add better defaults to client token generation when using an access token by consolidating client token defaults into ClientTokenGateway
- Add PaymentMethod#revoke

## 2.55.0

- Add VenmoAccount
- Add support for Set Transaction Context supplementary data

## 2.54.0

- Treat dispute date_opened and date_won attributes as Dates. Note: in versions 2.51.0-2.53.0, the dispute date_opened and date_won attributes were incorrectly parsed as strings. We pulled them off RubyGems to prevent the incorrect code from being downloaded.

## 2.53.0

- This version of the library was removed from RubyGems. See the note on 2.54.0 for further explanation.
- Adds options to skip avs and cvv checks for a single transaction

## 2.52.0

- This version of the library was removed from RubyGems. See the note on 2.54.0 for further explanation.
- Add Amex Express Checkout payment method
- Fix bug where Customer#payment_methods didn't include Android Pay cards

## 2.51.0

- This version of the library was removed from RubyGems. See the note on 2.54.0 for further explanation.
- Fixes bug with signature of partner oauth connect url
- Adds date_won, date_opened and kind to dispute webhook parsing
- Make grant a method on PaymentMethod and not just CreditCard

## 2.50.0

- Adds support for nonce granting to CreditCards
- Adds FacilitatorDetails for facilitated transactions
- Adds authorized_transaction_id, partial_settlement_transaction_ids and facilitator_details attr_readers to Transaction
- Adds support for Transaction#sale with raw Apple Pay parameters
- Adds Merchant.provision_raw_apple_pay
- Relaxes constraints on TransactionSearch#source
- Adds Check WebhookNotifications
- Adds Transaction.submit_for_partial_settlement

## 2.49.0

- Remove Amex Pay with Points response from Transaction.sale response
- Add expired? method to Apple Pay card
- Add customer_id property to +AndroidPayCard+, +ApplePayCard+, +CoinbaseAccount+, +EuropeBankAccount+, +PaypalAccount+, and +UnknownPaymentMethod+
- Add new error +ProcessorDoesNotSupportAuths+

## 2.48.1

- Fix issue in TestTransaction spec
- Fix issue with LibXML causing a segfault when using Ruby version 2.0.0

## 2.48.0

- Add support for Amex rewards transactions
- Add billing_agreement_id to PayPalAccount
- Fix bug in TestingGateway#check_environment

## 2.47.0

- Add {ApplePayDetails,ApplePayCard,AndroidPayDetails,AndroidPayCard}#source_description
- Add AndroidPayDetails#source_card_type, #source_card_last_4
- Add PaypalDetails#description, #transaction_fee_amount, #transaction_fee_currency_iso_code
- Add new card-specific Android Pay test nonces
- Add various other test nonces

## 2.46.0

- Add oauth support

## 2.45.0

- Add support for Android Pay

## 2.44.0

- Validate webhook challenge payload
- Changed CreditCardVerification::Status constants
- Add missing criteria to CreditCardVerification search

## 2.43.0

- Add 3DS info to server side

## 2.42.0

- Add {ApplePayCard,CoinbaseAccount}#default?
- Add {ApplePayCard,CoinbaseAccount} payment instrument constants
- Add European Bank Account test nonce

## 2.41.0

- Add support for new SEPA workflow

## 2.40.0

- Add 3D Secure transaction fields
- Add ability to create nonce from vaulted payment methods

## 2.39.0

- Surface Apple Pay payment instrument name in responses
- Support Coinbase payment instruments
- Improve support for SEPA payment instruments
- Upgrade RSpec and improve tests
- Update links to documentation

## 2.38.0

- Use OpenSSL::Digest instead of OpenSSL::Digest::Digest (Thanks, Michael Koziarski (@NZKoz))

## 2.37.0

- Add risk_data to Transaction and Verification with Kount decision and id
- Add verification_amount an option when creating a credit card
- Add TravelCruise industry type to Transaction
- Add room_rate to Lodging industry type
- Add CreditCard#verification as the latest verification on that credit card
- Add ApplePay support to all endpoints that may return ApplePayCard objects
- Align WebhookTesting with other client libraries

## 2.36.0

- Allow descriptor to be passed in Funding Details options params for Merchant Account create and update.

## 2.35.0

- Add additional_processor_response to transaction

## 2.34.1

- Allow payee_email to be passed in options params for Transaction create

## 2.34.0

- Added paypal specific fields to transaction calls
- Added SettlementPending, SettlementDeclined transaction statuses

## 2.33.1

- Update version number

## 2.33.0

- Allow credit card verification options to be passed outside of the nonce for PaymentMethod.create
- Allow billing_address parameters and billing_address_id to be passed outside of the nonce for PaymentMethod.create
- Add Subscriptions to paypal accounts
- Add PaymentMethod.update
- Add fail_on_duplicate_payment_method option to PaymentMethod.create
- Add Descriptor#url

## 2.32.0

- Official support for v.zero SDKs.

## 2.31.0

- Add support for lodging industry data

## 2.30.2

- Ensure that TR Data is encoded correctly

## 2.30.1

- Make webhook parsing more robust with newlines
- Add messages to InvalidSignature exceptions

## 2.30.0

- Include Dispute information on Transaction
- Search for Transactions disputed on a certain date

## 2.29.0

- Disbursement Webhooks
- Use OpenSSL::Digest instead of OpenSSL::Digest::Digest (Thanks Scott Rocher, scottrocher@gmail.com)

## 2.28.0

- Merchant account find API

## 2.27.0

- Merchant account update API
- Merchant account create API v2

## 2.26.0

- Official support for Partnerships
- Changed visibility of methods used in multi-tenancy

## 2.25.0

- Adds hold_in_escrow and hold_in_escrow! methods
- Add error codes for verification not supported error
- Add company_name and tax_id to merchant account create
- Updates webhook notification to provide errors and merchant account at the top level
- Adds cancel_release and cancel_release! methods
- Refactors transaction_gateway
- Adds release_from_escrow!
- Adds release_from_escrow functionality
- Adds owner_phone to merchant account signature.
- Adds merchant account phone error code.

## 2.24.0

- Adds device data to transactions, customers, and credit cards.

## 2.23.0

- Adds disbursement details to transactions.
- Adds image_url to transactions.

## 2.22.0

- Adds channel field to transactions.

## 2.21.0

- Add card type indicators to transactions and verifications

## 2.20.0

- Add additional card types for card type indicators
- Added ability to allow TR query parameters with no value (thanks @dmathieu!)

## 2.19.0

- Adds verification search

## 2.18.0

- Additional card information, such as prepaid, debit, commercial, Durbin regulated, healthcare, and payroll, are returned on credit card responses
- Allows transactions to be specified as recurring

## 2.17.0

- Adds prepaid attribute to credit cards (possible values: Yes, No, Unknown)

## 2.16.0

- Adds webhook gateways for parsing, verifying, and testing incoming
  notifications
- Adds Transaction.refund!(id, amount = nil)

## 2.15.0

- Adds unique_number_identifier attribute to CreditCard

## 2.14.0

- Adds search for duplicate credit cards given a payment method token
- Adds flag to fail saving credit card to vault if card is duplicate

## 2.13.4

- Allows both url encoded and decoded query string and hash

## 2.13.3

- Exposes plan_id on transactions
- Fixes GitHub issue #19 - Unescapes escaped characters in query string

## 2.13.2

- Added error code for invalid purchase order number
- Changes transparent redirect query string regexp to allow hash to appear
  anywhere in params string

## 2.13.1

- Made the production endpoint configurable

## 2.13.0

- Added new error code for merchant accounts that do not support refunds
- Added GEMSPEC file

## 2.12.0

- Added ability to retrieve all Plans, AddOns and Discounts
- Added Transaction cloning

## 2.11.0

- Added SettlementBatchSummary

## 2.10.2

- Added support for international Maestro cards with payer authentication

## 2.10.1

- Support builder >= 2.0
- Changed comments to point to new doc site

## 2.10.0

- Added subscription_details to Transaction
- Added flag to store in vault only when a transaction is successful
- Added new error code

## 2.9.1

- Added a new transaction state, AuthorizationExpired.
- Enabled searching by authorization_expired_at.

## 2.8.0

- Added next_billing_date and transaction_id to subscription search
- Added address_country_name to customer search
- Added new error codes

## 2.7.0

- Added advanced vault search for customers and payment methods
- Added dynamic descriptors
- Added level 2 fields to transactions:
  - tax_amount
  - tax_exempt
  - purchase_order_number

## 2.6.3

- Allow passing of existing shipping_address_id on new transactions

## 2.6.2

- Added billing_address_id to allowed parameters for credit cards create and update
- Allow searching on subscriptions that are currently in a trial period using in_trial_period

## 2.6.1

- Now supports ruby 1.9.1 and 1.9.2

## 2.6.0

- Added ability to perform multiple partial refunds on Transactions
- Deprecated Transaction refund_id in favor of refund_ids
- Added Braintree::Address::CountryNames, a list of the country names/codes that the gateway accepts (thanks r38y[https://github.com/r38y])
- Added revert_subscription_on_proration_failure flag to Subscription update that specifies how a Subscription should react to a failed proration charge
- Deprecated Subscription next_bill_amount in favor of next_billing_period_amount
- Added new fields to Subscription:
  - balance
  - paid_through_date
  - next_billing_period_amount

## 2.5.2

- Removed ssl expiration check
- Lazy initialize Configuration.logger when directly instantiating configuration

## 2.5.1

- Lazy initialize Configuration.logger to fix bug with ssl expiration check

## 2.5.0

- Added AddOns/Discounts
- Enhanced Subscription search
- Enhanced Transaction search
- Made gateway operations threadsafe when using multiple configurations
- Allowed prorate_charges to be specified on Subscription update
- Added AddOn/Discount details to Transactions that were created from a Subscription
- Added Expired and Pending statuses to Subscription
- Added constants for CreditCardVerification statuses
- Renamed GatewayRejectionReason constants to make them more idiomatic
- Removed 13 digit Visa Sandbox Credit Card number and replaced it with a 16 digit Visa
- Added refund class method on Transaction
- Deprecated instance methods on Resource classes in favor of class methods
- Added new fields to Subscription:
  - billing_day_of_month
  - days_past_due
  - first_billing_date
  - never_expires
  - number_of_billing_cycles

## 2.4.0

- Added unified message to result objects
- Added ability to specify country using country_name, country_code_alpha2, country_code_alpha3, or country_code_numeric (see ISO_3166-1[https://en.wikipedia.org/wiki/ISO_3166-1])
- Added gateway_rejection_reason to Transaction and Verification
- Added delete as a class method on CreditCard (in addition to the existing instance method)
- Allow searching with Date objects (in addition to DateTime and Time objects)
- When creating a Subscription, return failed transaction on the ErrorResult if the initial transaction is not successful

## 2.3.1

- Fixed gem packaging

## 2.3.0

- Removed dependency on libxml -- it will still be used if libxml is explicitly required or it will fall back on rexml
- Added unified TransparentRedirect url and confirm methods and deprecated old methods
- Allow updating the payment_method_token on a subscription
- Added methods to link a Transaction with its refund and vice versa
- Allow card verification against a specified merchant account
- Added ability to update a customer, credit card, and billing address in one request

## 2.2.0

- Prevent race condition when pulling back collection results -- search results represent the state of the data at the time the query was run
- Rename ResourceCollection's approximate_size to maximum_size because items that no longer match the query will not be returned in the result set
- Correctly handle HTTP error 426 (Upgrade Required) -- the error code is returned when your client library version is no longer compatible with the gateway

## 2.1.0

- Added transaction advanced search
- Added ability to partially refund transactions
- Added ability to manually retry past-due subscriptions
- Added new transaction error codes
- Allow merchant account to be specified when creating transactions
- Allow creating a transaction with a vault customer and new payment method
- Allow existing billing address to be updated when updating credit card

## 2.0.0

- Updated success? on transaction responses to return false on declined transactions
- Search results now include Enumerable and will automatically paginate data
- Added credit_card[cardholder_name] to allowed transaction params and CreditCardDetails (thanks chrismcc[https://github.com/chrismcc])

## 1.2.1

- Added ValidationErrorCollection#shallow_errors to get all of the ValidationErrors at a given level in the error hierarchy
- Added the ability to make a credit card the default card for a customer
- Added constants for transaction statuses
- Updated Quick Start in README.rdoc to show a workflow with error checking

## 1.2.0

- Added Subscription search
- Updated production CA SSL certificate authority
- Updated credit cards to include associated subscriptions when finding in vault
- Fixed bug where we used to raise a "forged query string" exception when we were down for maintenance.

## 1.1.3

- Fixed a bug with empty search results
- Added support for appending to user agent
- Finding a customer using id as an integer will now work (even though customer ids are actually strings)

## 1.1.2

- Allow passing expiration_month and expiration_year separately
- Updated Customer.find to raise an ArgumentError if given an invalid id
- Added error code for transaction amounts that are too large
- Include Enumerable in Braintree::Errors to iterate over all validation errors
- Added processor_authorization_code attr_reader to Braintree::Transaction
- Added cvv_response_code attr_reader to Braintree::Transaction
- Added deep_errors method to Braintree::ValidationErrorCollection to get errors at every level of nesting

## 1.1.1

- Added explicit require for date to fix missing initialize (thanks jherdman[https://github.com/jherdman])
- Allow Transaction price and Subscription amount as BigDecimals (as well as Strings)
- Ruby 1.9 bug fixes (thanks Leo Shemesh)

## 1.1.0

- Recurring billing support

## 1.0.1

- Custom fields support
- Transaction status history support

## 1.0.0

- Initial release
