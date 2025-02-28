---
title: AddCampaignCriterions Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
description: Adds one or more campaign criterions that help determine whether ads in each campaign get served.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# AddCampaignCriterions Service Operation - Campaign Management
Adds one or more campaign criterions that help determine whether ads in each campaign get served.

## <a name="request"></a>Request Elements
The *AddCampaignCriterionsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaigncriterions"></a>CampaignCriterions|A list of criterions that help determine whether ads in each campaign get served.<br/><br/>You can include up to 100 campaign criterions per request.|[CampaignCriterion](campaigncriterion.md) array|
|<a name="criteriontype"></a>CriterionType|The type of criterion to add, for example *Webpage*. You can specify only one criterion type value per call.<br/><br/>To add, delete, or update target criterions i.e., age, day and time, device, gender, location, location intent, and radius criterions, you must specify the *CriterionType* value as *Targets*. You can add, delete, and update multiple target criterion types in the same operation. To retrieve these target criterions via [GetCampaignCriterionsByIds](getcampaigncriterionsbyids.md) you must request the specific type individually i.e., *Age*, *DayTime*, *Device*, *Gender*, *Location*, *LocationIntent*, and *Radius*.|[CampaignCriterionType](campaigncriteriontype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddCampaignCriterionsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaigncriterionids"></a>CampaignCriterionIds|A list of unique system identifiers corresponding to the criterion that were added.<br/><br/>The list of identifiers corresponds directly to the list of criterion in the request. Items of the list may be returned as null. For each list index where a criterion was not added, the corresponding element will be null.|**long** array|
|<a name="nestedpartialerrors"></a>NestedPartialErrors|An array of [BatchErrorCollection](batcherrorcollection.md) objects that contain details for any criterion that were not successfully added. The top level error within each [BatchErrorCollection](batcherrorcollection.md) object corresponds to potential criterion errors. The nested list of [BatchError](batcherror.md) objects would include any errors specific to the list of items a criterion can have.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchErrorCollection](batcherrorcollection.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">AddCampaignCriterions</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <AddCampaignCriterionsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <CampaignCriterions i:nil="false">
        <CampaignCriterion i:type="-- derived type specified here with the appropriate prefix --">
          <CampaignId>ValueHere</CampaignId>
          <Criterion i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--These fields are applicable if the derived type attribute is set to HotelGroup-->
            <Listing i:nil="false">
              <Attribute i:nil="false">ValueHere</Attribute>
              <Operand i:nil="false">ValueHere</Operand>
            </Listing>
            <ListingType>ValueHere</ListingType>
            <ParentCriterionId i:nil="false">ValueHere</ParentCriterionId>
            <!--These fields are applicable if the derived type attribute is set to HotelAdvanceBookingWindowCriterion-->
            <MaxDays i:nil="false">ValueHere</MaxDays>
            <MinDays i:nil="false">ValueHere</MinDays>
            <!--These fields are applicable if the derived type attribute is set to HotelCheckInDateCriterion-->
            <EndDate i:nil="false">ValueHere</EndDate>
            <StartDate i:nil="false">ValueHere</StartDate>
            <!--This field is applicable if the derived type attribute is set to HotelCheckInDayCriterion-->
            <CheckInDay i:nil="false">ValueHere</CheckInDay>
            <!--This field is applicable if the derived type attribute is set to HotelDateSelectionTypeCriterion-->
            <HotelDateSelectionType i:nil="false">ValueHere</HotelDateSelectionType>
            <!--These fields are applicable if the derived type attribute is set to HotelLengthOfStayCriterion-->
            <MaxNights i:nil="false">ValueHere</MaxNights>
            <MinNights i:nil="false">ValueHere</MinNights>
            <!--This field is applicable if the derived type attribute is set to ProductScope-->
            <Conditions i:nil="false">
              <ProductCondition>
                <Attribute i:nil="false">ValueHere</Attribute>
                <Operand i:nil="false">ValueHere</Operand>
              </ProductCondition>
            </Conditions>
            <!--This field is applicable if the derived type attribute is set to Webpage-->
            <Parameter i:nil="false">
              <Conditions i:nil="false">
                <WebpageCondition>
                  <Argument i:nil="false">ValueHere</Argument>
                  <Operand>ValueHere</Operand>
                  <Operator i:nil="false">ValueHere</Operator>
                </WebpageCondition>
              </Conditions>
              <CriterionName i:nil="false">ValueHere</CriterionName>
            </Parameter>
            <!--This field is applicable if the derived type attribute is set to AgeCriterion-->
            <AgeRange i:nil="false">ValueHere</AgeRange>
            <!--These fields are applicable if the derived type attribute is set to DeviceCriterion-->
            <DeviceName i:nil="false">ValueHere</DeviceName>
            <OSName i:nil="false">ValueHere</OSName>
            <!--These fields are applicable if the derived type attribute is set to DayTimeCriterion-->
            <Day i:nil="false">ValueHere</Day>
            <FromHour i:nil="false">ValueHere</FromHour>
            <FromMinute i:nil="false">ValueHere</FromMinute>
            <ToHour i:nil="false">ValueHere</ToHour>
            <ToMinute i:nil="false">ValueHere</ToMinute>
            <!--This field is applicable if the derived type attribute is set to GenderCriterion-->
            <GenderType i:nil="false">ValueHere</GenderType>
            <!--These fields are applicable if the derived type attribute is set to RadiusCriterion-->
            <LatitudeDegrees i:nil="false">ValueHere</LatitudeDegrees>
            <LongitudeDegrees i:nil="false">ValueHere</LongitudeDegrees>
            <Name i:nil="false">ValueHere</Name>
            <Radius i:nil="false">ValueHere</Radius>
            <RadiusUnit i:nil="false">ValueHere</RadiusUnit>
            <!--These fields are applicable if the derived type attribute is set to LocationCriterion-->
            <DisplayName i:nil="false">ValueHere</DisplayName>
            <EnclosedLocationIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
              <a1:long>ValueHere</a1:long>
            </EnclosedLocationIds>
            <LocationId i:nil="false">ValueHere</LocationId>
            <LocationType i:nil="false">ValueHere</LocationType>
            <!--This field is applicable if the derived type attribute is set to LocationIntentCriterion-->
            <IntentOption i:nil="false">ValueHere</IntentOption>
            <!--These fields are applicable if the derived type attribute is set to AudienceCriterion-->
            <AudienceId i:nil="false">ValueHere</AudienceId>
            <AudienceType i:nil="false">ValueHere</AudienceType>
            <!--These fields are applicable if the derived type attribute is set to ProfileCriterion-->
            <ProfileId>ValueHere</ProfileId>
            <ProfileType>ValueHere</ProfileType>
            <!--This field is applicable if the derived type attribute is set to StoreCriterion-->
            <StoreId i:nil="false">ValueHere</StoreId>
          </Criterion>
          <ForwardCompatibilityMap xmlns:e30="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e30:KeyValuePairOfstringstring>
              <e30:key i:nil="false">ValueHere</e30:key>
              <e30:value i:nil="false">ValueHere</e30:value>
            </e30:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <Status i:nil="false">ValueHere</Status>
          <Type i:nil="false">ValueHere</Type>
          <!--No additional fields are applicable if the derived type attribute is set to NegativeCampaignCriterion-->
          <!--These fields are applicable if the derived type attribute is set to BiddableCampaignCriterion-->
          <CriterionBid i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to RateBid-->
            <RateAmount i:nil="false">
              <Amount i:nil="false">ValueHere</Amount>
            </RateAmount>
            <!--This field is applicable if the derived type attribute is set to FixedBid-->
            <Amount>ValueHere</Amount>
            <!--This field is applicable if the derived type attribute is set to BidMultiplier-->
            <Multiplier>ValueHere</Multiplier>
          </CriterionBid>
          <CriterionCashback i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to CashbackAdjustment-->
            <CashbackPercent i:nil="false">ValueHere</CashbackPercent>
          </CriterionCashback>
        </CampaignCriterion>
      </CampaignCriterions>
      <CriterionType>ValueHere</CriterionType>
    </AddCampaignCriterionsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <AddCampaignCriterionsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <CampaignCriterionIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </CampaignCriterionIds>
      <NestedPartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchErrorCollection d4p1:type="-- derived type specified here with the appropriate prefix --">
          <BatchErrors d4p1:nil="false">
            <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Code>ValueHere</Code>
              <Details d4p1:nil="false">ValueHere</Details>
              <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
              <FieldPath d4p1:nil="false">ValueHere</FieldPath>
              <ForwardCompatibilityMap xmlns:e31="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
                <e31:KeyValuePairOfstringstring>
                  <e31:key d4p1:nil="false">ValueHere</e31:key>
                  <e31:value d4p1:nil="false">ValueHere</e31:value>
                </e31:KeyValuePairOfstringstring>
              </ForwardCompatibilityMap>
              <Index>ValueHere</Index>
              <Message d4p1:nil="false">ValueHere</Message>
              <Type d4p1:nil="false">ValueHere</Type>
              <!--These fields are applicable if the derived type attribute is set to EditorialError-->
              <Appealable d4p1:nil="false">ValueHere</Appealable>
              <DisapprovedText d4p1:nil="false">ValueHere</DisapprovedText>
              <Location d4p1:nil="false">ValueHere</Location>
              <PublisherCountry d4p1:nil="false">ValueHere</PublisherCountry>
              <ReasonCode>ValueHere</ReasonCode>
            </BatchError>
          </BatchErrors>
          <Code d4p1:nil="false">ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e32="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e32:KeyValuePairOfstringstring>
              <e32:key d4p1:nil="false">ValueHere</e32:key>
              <e32:value d4p1:nil="false">ValueHere</e32:value>
            </e32:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to EditorialErrorCollection-->
          <Appealable d4p1:nil="false">ValueHere</Appealable>
          <DisapprovedText d4p1:nil="false">ValueHere</DisapprovedText>
          <Location d4p1:nil="false">ValueHere</Location>
          <PublisherCountry d4p1:nil="false">ValueHere</PublisherCountry>
          <ReasonCode>ValueHere</ReasonCode>
        </BatchErrorCollection>
      </NestedPartialErrors>
    </AddCampaignCriterionsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddCampaignCriterionsResponse> AddCampaignCriterionsAsync(
	IList<CampaignCriterion> campaignCriterions,
	CampaignCriterionType criterionType)
{
	var request = new AddCampaignCriterionsRequest
	{
		CampaignCriterions = campaignCriterions,
		CriterionType = criterionType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddCampaignCriterionsAsync(r), request));
}
```
```java
static AddCampaignCriterionsResponse addCampaignCriterions(
	ArrayOfCampaignCriterion campaignCriterions,
	ArrayList<CampaignCriterionType> criterionType) throws RemoteException, Exception
{
	AddCampaignCriterionsRequest request = new AddCampaignCriterionsRequest();

	request.setCampaignCriterions(campaignCriterions);
	request.setCriterionType(criterionType);

	return CampaignManagementService.getService().addCampaignCriterions(request);
}
```
```php
static function AddCampaignCriterions(
	$campaignCriterions,
	$criterionType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddCampaignCriterionsRequest();

	$request->CampaignCriterions = $campaignCriterions;
	$request->CriterionType = $criterionType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddCampaignCriterions($request);
}
```
```python
response=campaignmanagement_service.AddCampaignCriterions(
	CampaignCriterions=CampaignCriterions,
	CriterionType=CriterionType)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

