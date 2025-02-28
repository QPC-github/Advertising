---
title: AddAdGroups Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
description: Adds new ad groups to a specified campaign.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# AddAdGroups Service Operation - Campaign Management
Adds new ad groups to a specified campaign.

## <a name="request"></a>Request Elements
The *AddAdGroupsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroups"></a>AdGroups|An array of [AdGroup](adgroup.md) objects to add to the specified campaign.<br/><br/>You can add a maximum of 1,000 ad groups in a single call. Each campaign can have up to 20,000 ad groups.|[AdGroup](adgroup.md) array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to add the ad groups to.|**long**|
|<a name="returninheritedbidstrategytypes"></a>ReturnInheritedBidStrategyTypes|Reserved for future use.|**boolean**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddAdGroupsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupids"></a>AdGroupIds|A list of unique system identifiers corresponding to the ad groups that were added.<br/><br/>The list of identifiers corresponds directly to the list of ad groups in the request. Items of the list may be returned as null. For each list index where an ad group was not added, the corresponding element will be null.|**long** array|
|<a name="inheritedbidstrategytypes"></a>InheritedBidStrategyTypes|Reserved for future use.|**string** array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">AddAdGroups</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <AddAdGroupsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <CampaignId>ValueHere</CampaignId>
      <AdGroups i:nil="false">
        <AdGroup>
          <AdRotation i:nil="false">
            <EndDate i:nil="false">ValueHere</EndDate>
            <StartDate i:nil="false">ValueHere</StartDate>
            <Type i:nil="false">ValueHere</Type>
          </AdRotation>
          <AudienceAdsBidAdjustment i:nil="false">ValueHere</AudienceAdsBidAdjustment>
          <BiddingScheme i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpcBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpvBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpmBiddingScheme-->
            <!--This field is applicable if the derived type attribute is set to InheritFromParentBiddingScheme-->
            <InheritedBidStrategyType i:nil="false">ValueHere</InheritedBidStrategyType>
            <!--This field is applicable if the derived type attribute is set to PercentCpcBiddingScheme-->
            <MaxPercentCpc i:nil="false">ValueHere</MaxPercentCpc>
            <!--This field is applicable if the derived type attribute is set to CommissionBiddingScheme-->
            <CommissionRate i:nil="false">ValueHere</CommissionRate>
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpaBiddingScheme-->
            <!--This field is applicable if the derived type attribute is set to CostPerSaleBiddingScheme-->
            <TargetCostPerSale i:nil="false">ValueHere</TargetCostPerSale>
          </BiddingScheme>
          <CommissionRate i:nil="false">
            <RateAmount i:nil="false">
              <Amount i:nil="false">ValueHere</Amount>
            </RateAmount>
          </CommissionRate>
          <CpcBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </CpcBid>
          <EndDate i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </EndDate>
          <FinalUrlSuffix i:nil="false">ValueHere</FinalUrlSuffix>
          <ForwardCompatibilityMap xmlns:e20="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e20:KeyValuePairOfstringstring>
              <e20:key i:nil="false">ValueHere</e20:key>
              <e20:value i:nil="false">ValueHere</e20:value>
            </e20:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <FrequencyCapSettings i:nil="false">
            <FrequencyCapSettings>
              <CapValue>ValueHere</CapValue>
              <FrequencyCapUnit i:nil="false">ValueHere</FrequencyCapUnit>
              <TimeGranularity>ValueHere</TimeGranularity>
            </FrequencyCapSettings>
          </FrequencyCapSettings>
          <Id i:nil="false">ValueHere</Id>
          <Language i:nil="false">ValueHere</Language>
          <MultimediaAdsBidAdjustment i:nil="false">ValueHere</MultimediaAdsBidAdjustment>
          <Name i:nil="false">ValueHere</Name>
          <Network i:nil="false">ValueHere</Network>
          <PercentCpcBid i:nil="false">
            <RateAmount i:nil="false">
              <Amount i:nil="false">ValueHere</Amount>
            </RateAmount>
          </PercentCpcBid>
          <PrivacyStatus i:nil="false">ValueHere</PrivacyStatus>
          <Settings i:nil="false">
            <Setting i:type="-- derived type specified here with the appropriate prefix --">
              <Type i:nil="false">ValueHere</Type>
              <!--This field is applicable if the derived type attribute is set to DynamicFeedSetting-->
              <FeedId i:nil="false">ValueHere</FeedId>
              <!--This field is applicable if the derived type attribute is set to TargetSetting-->
              <Details i:nil="false">
                <TargetSettingDetail>
                  <CriterionTypeGroup>ValueHere</CriterionTypeGroup>
                  <TargetAndBid>ValueHere</TargetAndBid>
                </TargetSettingDetail>
              </Details>
              <!--These fields are applicable if the derived type attribute is set to CoOpSetting-->
              <BidBoostValue i:nil="false">ValueHere</BidBoostValue>
              <BidMaxValue i:nil="false">ValueHere</BidMaxValue>
              <BidOption i:nil="false">ValueHere</BidOption>
              <!--This field is applicable if the derived type attribute is set to VerifiedTrackingSetting-->
              <Details xmlns:e21="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
                <e21:ArrayOfKeyValuePairOfstringstring>
                  <e21:KeyValuePairOfstringstring>
                    <e21:key i:nil="false">ValueHere</e21:key>
                    <e21:value i:nil="false">ValueHere</e21:value>
                  </e21:KeyValuePairOfstringstring>
                </e21:ArrayOfKeyValuePairOfstringstring>
              </Details>
              <!--This field is applicable if the derived type attribute is set to DisclaimerSetting-->
              <DisclaimerAdsEnabled>ValueHere</DisclaimerAdsEnabled>
              <!--This field is applicable if the derived type attribute is set to HotelSetting-->
              <HotelAdGroupType>ValueHere</HotelAdGroupType>
              <!--This field is applicable if the derived type attribute is set to ResponsiveSearchAdsSetting-->
              <AutoGeneratedAssetsEnabled i:nil="false">ValueHere</AutoGeneratedAssetsEnabled>
              <!--This field is applicable if the derived type attribute is set to PerformanceMaxSetting-->
              <FinalUrlExpansionOptOut>ValueHere</FinalUrlExpansionOptOut>
            </Setting>
          </Settings>
          <StartDate i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </StartDate>
          <Status i:nil="false">ValueHere</Status>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters i:nil="false">
            <Parameters i:nil="false">
              <CustomParameter>
                <Key i:nil="false">ValueHere</Key>
                <Value i:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <UseOptimizedTargeting i:nil="false">ValueHere</UseOptimizedTargeting>
          <AdScheduleUseSearcherTimeZone i:nil="false">ValueHere</AdScheduleUseSearcherTimeZone>
          <AdGroupType i:nil="false">ValueHere</AdGroupType>
          <CpvBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </CpvBid>
          <CpmBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </CpmBid>
          <McpaBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </McpaBid>
        </AdGroup>
      </AdGroups>
      <ReturnInheritedBidStrategyTypes i:nil="false">ValueHere</ReturnInheritedBidStrategyTypes>
    </AddAdGroupsRequest>
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
    <AddAdGroupsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AdGroupIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </AdGroupIds>
      <InheritedBidStrategyTypes d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:string>ValueHere</a1:string>
      </InheritedBidStrategyTypes>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e22="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e22:KeyValuePairOfstringstring>
              <e22:key d4p1:nil="false">ValueHere</e22:key>
              <e22:value d4p1:nil="false">ValueHere</e22:value>
            </e22:KeyValuePairOfstringstring>
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
      </PartialErrors>
    </AddAdGroupsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddAdGroupsResponse> AddAdGroupsAsync(
	long campaignId,
	IList<AdGroup> adGroups,
	bool? returnInheritedBidStrategyTypes)
{
	var request = new AddAdGroupsRequest
	{
		CampaignId = campaignId,
		AdGroups = adGroups,
		ReturnInheritedBidStrategyTypes = returnInheritedBidStrategyTypes
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddAdGroupsAsync(r), request));
}
```
```java
static AddAdGroupsResponse addAdGroups(
	java.lang.Long campaignId,
	ArrayOfAdGroup adGroups,
	boolean returnInheritedBidStrategyTypes) throws RemoteException, Exception
{
	AddAdGroupsRequest request = new AddAdGroupsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroups(adGroups);
	request.setReturnInheritedBidStrategyTypes(returnInheritedBidStrategyTypes);

	return CampaignManagementService.getService().addAdGroups(request);
}
```
```php
static function AddAdGroups(
	$campaignId,
	$adGroups,
	$returnInheritedBidStrategyTypes)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddAdGroupsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroups = $adGroups;
	$request->ReturnInheritedBidStrategyTypes = $returnInheritedBidStrategyTypes;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddAdGroups($request);
}
```
```python
response=campaignmanagement_service.AddAdGroups(
	CampaignId=CampaignId,
	AdGroups=AdGroups,
	ReturnInheritedBidStrategyTypes=ReturnInheritedBidStrategyTypes)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

