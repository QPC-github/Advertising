---
title: GenderDimension Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
description: Reserved.
---
# GenderDimension Data Object - Campaign Management
Reserved.

## Syntax
```xml
<xs:complexType name="GenderDimension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AudienceGroupDimension">
      <xs:sequence>
        <xs:element minOccurs="0" name="GenderTypes" nillable="true" type="tns:ArrayOfGenderType" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [GenderDimension](genderdimension.md) object has the following elements: [GenderTypes](#gendertypes).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="gendertypes"></a>GenderTypes|Reserved.|[GenderType](gendertype.md) array|

The [GenderDimension](genderdimension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsaudiencegroupdimension"></a>Inherited Elements from AudienceGroupDimension
The [GenderDimension](genderdimension.md) object derives from the [AudienceGroupDimension](audiencegroupdimension.md) object, and inherits the following elements: [Type](#type). The descriptions below are specific to [GenderDimension](genderdimension.md), and might not apply to other objects that inherit the same elements from the [AudienceGroupDimension](audiencegroupdimension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|Reserved.|[AudienceGroupDimensionType](audiencegroupdimensiontype.md)|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

