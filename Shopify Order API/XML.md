## Created XML:

```xml
<entity-engine-xml>   

<!-- User -->

<Party 
    partyId="10010" 
    partyTypeId="PERSON" 
    preferredCurrencyUomId="USD" 
    statusId="PARTY_ENABLED"
    externalId="7133450502397"
/>

<Person 
    firstName="Muskan" 
    lastName="Pahwa" 
    partyId="10010"
    createdStamp= "2024-01-19T04:06:05-05:00"
    lastUpdatedStamp= "2024-02-12T06:11:22-05:00"
/> 

<!-- Default address - general correspondence address -->

<ContactMech 
    contactMechId="CM1004" 
    contactMechTypeId="POSTAL_ADDRESS" 
/>

<PostalAddress 
    address1="12th Street Northwest" 
    city="Washington" 
    contactMechId="CM1004" 
    countyGeoId="USA" 
    createdStamp="2024-02-15 11:50:52.047" 
    postalCode="20008" 
    stateProvinceGeoId="DC" 
    toName="Muskan Pahwa"
/> 

<PartyContactMechPurpose 
    contactMechId="CM1004" 
    contactMechPurposeTypeId="GENERAL_LOCATION" 
    fromDate="2024-02-15 00:00:00.0" 
    partyId="10010"
/>

<PartyContactMech 
    contactMechId="CM1004" 
    fromDate="2024-02-15 00:00:00.0" 
    partyId="10010"
/> 

<!-- Email Address -->

<ContactMech 
    contactMechId="CM1000" 
    contactMechTypeId="EMAIL_ADDRESS" 
    infoString="customer@example.com" 
/>

<PartyContactMech 
    contactMechId="CM1000" 
    partyId="10010"
    fromDate="2024-02-08 18:19:08.508" 
/>

<PartyContactMechPurpose 
    contactMechId="CM1000" 
    contactMechPurposeTypeId="PRIMARY_EMAIL" 
    fromDate="2024-02-15 00:00:00.0" 
    partyId="10010"
/>

<!-- Product -->

<!-- Virtual Product -->

<Product 
    productId="BSK-S-P" 
    productName="Beaumont Summit Kit" 
    internalName="Beaumont Summit Kit" 
    isVariant="N" 
    isVirtual="Y" 
    productTypeId="FINISHED_GOOD" 
    inventoryItemTypeId="SERIALIZED_INV_ITEM" 
/>

<!-- Variant Product -->

<Product
    productId="BSK-S"
    productName="Beaumont Summit Kit - S / Yellow"
    internalName="Beaumont Summit Kit - S / Yellow"
    isVariant="Y"
    isVirtual="N"
    productWeight="300.000000"
    weightUomId="WT_g"
    productTypeId="FINISHED_GOOD"
    inventoryItemTypeId="SERIALIZED_INV_ITEM"
/>

<GoodIdentification 
    goodIdentificationTypeId="SKU" 
    idValue="MJ01-S-Yellow"
    productId="BSK-S"
/>

<!-- Association of virtual-variant product -->

<ProductAssoc
    productId="BSK-S-P"
    productIdTo="BSK-S"
    productAssocTypeId="PRODUCT_VARIANT"
    sequenceNum="10"
/>

<!-- Product Features -->

<ProductFeatureAppl
    productFeatureId="TEXT_SMALL"
    productId="BSK-S-P"
    fromDate="2024-02-20 09:45:21.079"
    productFeatureApplTypeId="SELECTABLE_FEATURE"
    sequenceNum="1"
/>

<ProductFeatureAppl
    productFeatureId="TEXT_YELLOW"
    fromDate="2024-02-20 09:45:21.038"
    productFeatureApplTypeId="SELECTABLE_FEATURE"
    productId="BSK-S-P"
    sequenceNum="7"
/>


<ProductFeatureAppl
    productFeatureId="TEXT_SMALL"
    productId="BSK-S"
    fromDate="2024-02-20 09:45:50.271"
    productFeatureApplTypeId="STANDARD_FEATURE"
    sequenceNum="1"
/>

<ProductFeatureAppl
    productId="BSK-S"
    productFeatureId="TEXT_YELLOW"
    fromDate="2024-02-20 09:45:50.271"
    productFeatureApplTypeId="STANDARD_FEATURE"
    sequenceNum="7"
/>

<!-- Price -->

<ProductPrice
    price="42.000"
    productId="BSK-S"
    productPricePurposeId="COMPONENT_PRICE"
    productPriceTypeId="DEFAULT_PRICE"
    currencyUomId="USD"
    productStoreGroupId="_NA_"
    fromDate="2004-08-20 12:55:36.479"
/>

<!-- Creating Order -->

<OrderHeader 
    orderId="ODR100" 
    orderTypeId="SALES_ORDER" 
    externalId="5524198818045"
    statusId="ORDER_APPROVED" 
    createdBy="shannee" 
    currencyUom="USD" 
    grandTotal="46.90" 
    invoicePerShipment="Y" 
    orderDate="2024-02-12T05:54:23-05:00" 
    lastUpdatedStamp="2024-02-12T05:54:32-05:00"
    originFacilityId="WebStoreWarehouse" 
    priority="2" 
    productStoreId="9000" 
    remainingSubTotal="107.37" 
    salesChannelEnumId="WEB_SALES_CHANNEL" 
    visitId="10321" 
    webSiteId="WebStore"
/> 

<OrderAttribute 
    orderId="ODR100"
    attrName="TYPE" 
    attrValue="PREORDER" 
/> 

<OrderItem 
    orderId="ODR100" 
    orderItemSeqId="00001" 
    itemDescription="Beaumont Summit Kit - S / Yellow" 
    statusId="ITEM_APPROVED" 
    unitPrice="42.00"
    externalId="13665324204285"
    orderItemTypeId="PRODUCT_ORDER_ITEM" 
    prodCatalogId="Clothing" 
    productId="BSK-S" 
    quantity="1" 
    autoCancelDate="2024-02-24 12:08:42.332" 
    changeByUserLoginId="johnhays" 
    correspondingPoId="" 
    isModifiedPrice="N" 
    isPromo="N" 
/>

<OrderStatus 
    orderId="ODR100" 
    orderStatusId="2500" 
    statusDatetime="2024-02-12T05:54:26-05:00" 
    statusId="ORDER_APPROVED" 
/>

<!-- Vendor -->

<Party 
    partyId="ven-hotwax" 
    partyTypeId="LEGAL_ORGANIZATION"
/>

<Vendor 
    partyId="ven-hotwax"
    manifestCompanyName="Hotwax" 
    manifestCompanyTitle="Hotwax" 
/> 

<PartyRole 
    partyId="ven-hotwax" 
    roleTypeId="VENDOR"
/> 

<!-- Associating product with vendor -->

<VendorProduct 
    productId="BSK-S" 
    vendorPartyId="ven-hotwax"
    productStoreGroupId="_NA_" 
/> 

<!-- Creating preorder facility -->

<FacilityType 
    facilityTypeId="PRE_ORDER"
/>

<Facility 
    facilityId="PRE_ORDER_PARKING" 
    facilityName="Preorder Parking" 
    facilityTypeId="PRE_ORDER" 
/> 

<!-- Ship Group -->

<OrderItemShipGroup 
    orderId="ODR100" 
    shipGroupSeqId="1" 
    facilityId="PREORDER_PARKING"
    vendorPartyId="ven-hotwax"
    shipmentMethodTypeId="GROUND"
    contactMechId="CM1001" 
    carrierPartyId="FEDEX" 
    carrierRoleTypeId="CARRIER" 
/> 
 
<OrderItemShipGroupAssoc 
    orderId="ODR100" 
    orderItemSeqId="00001" 
    quantity="1.00" 
    shipGroupSeqId="1"
/> 

<!-- Order Adjustment -->

<OrderAdjustment 
    orderAdjustmentId="8011" 
    orderId="ODR100" 
    orderItemSeqId="00001" 
    amount="4.90" 
    orderAdjustmentTypeId="SHIPPING_CHARGES" 
    shipGroupSeqId="00001"
/> 

<!-- Adding Billing Address -->

<ContactMech 
    contactMechId="CM1001" 
    contactMechTypeId="POSTAL_ADDRESS" 
    createdStamp="2024-02-15 11:39:34.764" 
/>

<PostalAddress 
    toName="Muskan Pahwa"
    address1="12th S St NW" 
    city="Washington" 
    contactMechId="CM1001" 
    countyGeoId="USA" 
    postalCode="20008" 
    stateProvinceGeoId="DC" 
    createdStamp="2024-02-15 11:50:52.047" 
/> 

<OrderContactMech 
    contactMechId="CM1001" 
    contactMechPurposeTypeId="BILLING_LOCATION" 
    orderId="ODR100"
/>

<!-- Shipping address -->

<ContactMech 
    contactMechId="CM1002" 
    contactMechTypeId="POSTAL_ADDRESS" 
    createdStamp="2024-02-15 11:39:34.764" 
/>

<PostalAddress 
    address1="12th S St NW" 
    city="Washington" 
    contactMechId="CM1002" 
    countyGeoId="USA" 
    postalCode="20008" 
    stateProvinceGeoId="DC" 
    toName="Muskan Pahwa"
    latitude="38.9140405"
    longitude="-77.0532386"
/> 

<OrderContactMech 
    contactMechId="CM1002" 
    contactMechPurposeTypeId="SHIPPING_LOCATION" 
    orderId="ODR100"
/>

<!-- Payment -->

<PaymentMethodType 
    description="Shopify Payment" 
    paymentMethodTypeId="EXT_SHOPIFY"
/>

<OrderPaymentPreference 
    orderPaymentPreferenceId="OPM1000" 
    paymentMethodTypeId="EXT_SHOPIFY"
    orderId="ODR100" 
    orderItemSeqId="00001" 
    shipGroupSeqId="1" 
    statusId="PAYMENT_AUTHORIZED"
/>

</entity-engine-xml>
```

## Changes made in data model:

- Updating sql-type for higher precision of 11 to store latitude and logitude

   *fieldtypemysql.xml*

```xml
<field-type-def type="fixed-point" sql-type="DECIMAL(18,11)" java-type="java.math.BigDecimal"/>
```

- Adding two new fields in PostalAddress entity to store latitude and logitutde

   *party-entitymodel.xml | entity-name="PostalAddress"*

```xml
<field name="longitude" type="fixed-point"></field>
<field name="latitude" type="fixed-point"></field>
```