```json
{
  "order": {
    "id": "OrderHeader.externalId",
    "confirmed": "OrderHeader.statusId",
    "currency": "OrderHeader.currencyUom",
    "current_total_price": "OrderHeader.grandTotal",
    "email": "ContactMech.infoString",
    "financial_status": "OrderPaymentPreference.statusId",
    "payment_gateway_names": [
      {
        "shopify_payments": "OrderPaymentPreference.paymentMethodTypeId"
      }
    ],
    "phone": null,
    "source_name": "OrderHeader.salesChannelEnumId",
    "total_tip_received": "0.00",
    "billing_address": {
      "address1": "PostalAddress.address1",
      "phone": "TelecomNumber.contactNumber",
      "city": "PostalAddress.city",
      "zip": "PostalAddress.postalCode",
      "latitude": "PostalAddress.latitude",
      "longitude": "PostalAddress.longitude",
      "name": "PostalAddress.toName",
      "country_code": "PostalAddress.countryGeoId",
      "province_code": "PostalAddress.stateProvinceGeoId"
    },
    "customer": {
      "id": "Party.externalId",
      "email": "ContactMech.infoString",
      "first_name": "Person.firstName",
      "last_name": "Person.lastName",
      "verified_email": "PartyContactMech.verified",
      "currency": "Party.preferredCurrencyUomId",
      "default_address": {
        "address1": "PostalAddress.address1",
        "city": "PostalAddress.city",
        "zip": "PostalAddress.postalCode",
        "name": "PostalAddress.toName",
        "province_code": "PostalAddress.stateProvinceGeoId",
        "country_code": "PostalAddress.countryGeoId"
      }
    },
    "line_items": [
      {
        "id": "OrderItem.externalId",
        "name": "Product.productName",
        "price": "ProductPrice.price",
        "product_id": "GoodIdentification.idValue",
        "quantity": "OrderItem.quantity",
        "sku": "GoodIdentification.idValue",
        "taxable": "Product.taxable",
        "variant_id": "GoodIdentification.idValue",
        "vendor": "VendorProduct.productStoreGroupId"
      }
    ],
    "shipping_address": {
      "address1": "PostalAddress.address1",
      "phone": "TelecomNumber.contactNumber",
      "city": "PostalAddress.city",
      "zip": "PostalAddress.postalCode",
      "latitude": "PostalAddress.latitude",
      "longitude": "PostalAddress.longitude",
      "name": "PostalAddress.toName",
      "country_code": "PostalAddress.countryGeoId",
      "province_code": "PostalAddress.stateProvinceGeoId"
    },
    "shipping_lines": [
      {
        "price": "OrderAdjustment.amount"
      }
    ]
    // Additional Entities: 
    "OrderAdjustment.orderAdjustmentTypeId": "SHIPPING_CHARGES"
  }
}

```
