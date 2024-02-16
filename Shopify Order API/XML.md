## Changes made in data model:

- Since preorder type is not avaialbe so inserting one in order type table

```sql
INSERT INTO order_type (ORDER_TYPE_ID, DESCRIPTION)
VALUES ('PREORDER', 'Order for products not yet available for immediate delivery');
```


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

## Created XML:

```xml
<entity-engine-xml>   

<!-- Creating user -->

<Person 
    firstName="Muskan" 
    lastName="Pahwa" 
    partyId="10010"
    createdStamp= "2024-01-19T04:06:05-05:00"
    lastUpdatedStamp= "2024-02-12T06:11:22-05:00"
/> 

<Party 
    partyId="10010" 
    partyTypeId="PERSON" 
    preferredCurrencyUomId="USD" 
    statusId="PARTY_ENABLED"
    externalId="7133450502397"
/>

<!-- Adding default address - general correspondence address -->

<ContactMech 
    contactMechId="CM1002" 
    contactMechTypeId="POSTAL_ADDRESS" 
    createdStamp="2024-02-15 12:14:41.625" lastUpdatedStamp="2024-02-15 12:14:41.625"
/>

<PostalAddress 
    address1="12th Street Northwest" 
    city="Washington" 
    contactMechId="CM1002" 
    countyGeoId="USA" 
    createdStamp="2024-02-15 11:50:52.047" 
    postalCode="20008" 
    stateProvinceGeoId="DC" 
    toName="Muskan Pahwa"
/> 

<PartyContactMechPurpose 
    contactMechId="CM1002" 
    contactMechPurposeTypeId="GENERAL_LOCATION" 
    fromDate="2024-02-15 00:00:00.0" 
    partyId="10010"
/>

<PartyContactMech 
    contactMechId="CM1002" 
    fromDate="2024-02-15 00:00:00.0" 
    partyId="10010"
/> 

<!-- Creating Order -->

<OrderHeader 
    orderId="ODR100" 
    orderTypeId="PREORDER" 
    externalId="5524198818045"
    statusId="ORDER_APPROVED" 
    createdBy="marktailor" 
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



<OrderItem 
    orderId="ODR100" 
    orderItemSeqId="00005" 
    itemDescription="Beaumont Summit Kit - S / Yellow" 
    statusId="ITEM_CREATED" 
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


<OrderAdjustment 
    orderId="ODR100" 
    orderItemSeqId="00005" 
    amount="4.90" 
    createdByUserLogin="admin" 
    createdDate="2024-02-12T05:54:26-05:00" 
    orderAdjustmentId="8011" 
    orderAdjustmentTypeId="SHIPPING_CHARGES" 
    shipGroupSeqId="00005"
/> 


<ContactMech 
    contactMechId="CM1000" 
    contactMechTypeId="EMAIL_ADDRESS" 
    infoString="customer@example.com" 
/>

<PartyContactMech 
    contactMechId="CM1000" 
    partyId="10000"
    fromDate="2024-02-08 18:19:08.508" 
/>


<!-- Adding Billing Address -->

<ContactMech 
    contactMechId="CM1001" 
    contactMechTypeId="POSTAL_ADDRESS" 
    createdStamp="2024-02-15 11:39:34.764" 
/>

<PostalAddress 
    address1="12th S St NW" 
    city="Washington" 
    contactMechId="CM1001" 
    countyGeoId="USA" 
    createdStamp="2024-02-15 11:50:52.047" 
    postalCode="20008" 
    stateProvinceGeoId="DC" 
    toName="Muskan Pahwa"
/> 

<PartyContactMechPurpose 
    contactMechId="CM1001" 
    contactMechPurposeTypeId="BILLING_LOCATION" 
    fromDate="2024-02-15 00:00:00.0" 
    partyId="10010"
/>

<PartyContactMech 
    contactMechId="CM1001" 
    fromDate="2024-02-15 00:00:00.0" 
    partyId="10010"
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
    createdStamp="2024-02-15 11:50:52.047" 
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

</entity-engine-xml>
```


## Explaination of Mapping


- Customer JSON to a Person and Party:
  - JSON
  ```json
   "customer": {
      "id": 7133450502397,
      "email": "customer@example.com",
      "created_at": "2024-01-19T04:06:05-05:00",
      "updated_at": "2024-02-12T06:11:22-05:00",
      "first_name": "Muskan",
      "last_name": "Pahwa",
      "currency": "USD"
    }
  ```
  - XML
  ```xml
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
  ```

- Default address to general address:
  - JSON
    ```json
    "default_address": {
        "id": 8819900711165,
        "customer_id": 7133450502397,
        "first_name": "Muskan",
        "last_name": "Pahwa",
        "company": null,
        "address1": "12th Street Northwest",
        "address2": null,
        "city": "Washington",
        "province": "District of Columbia",
        "country": "United States",
        "zip": "20008",
        "phone": null,
        "name": "Muskan Pahwa",
        "province_code": "DC",
        "country_code": "US",
        "country_name": "United States",
        "default": true
      }
    ```
  - XML
    ```xml
    <ContactMech 
    contactMechId="CM1002" 
    contactMechTypeId="POSTAL_ADDRESS" 
    createdStamp="2024-02-15 12:14:41.625" lastUpdatedStamp="2024-02-15 12:14:41.625"
    />

    <PostalAddress 
    address1="12th Street Northwest" 
    city="Washington" 
    contactMechId="CM1002" 
    countyGeoId="USA" 
    createdStamp="2024-02-15 11:50:52.047" 
    postalCode="20008" 
    stateProvinceGeoId="DC" 
    toName="Muskan Pahwa"
    /> 

    <PartyContactMechPurpose 
      contactMechId="CM1002" 
      contactMechPurposeTypeId="GENERAL_LOCATION" 
      fromDate="2024-02-15 00:00:00.0" 
      partyId="10010"
    />

    <PartyContactMech 
      contactMechId="CM1002" 
      fromDate="2024-02-15 00:00:00.0" 
      partyId="10010"
    /> 
    ```

- 
