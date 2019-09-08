---
title: IAppIdAuthority 接口
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91ab2f71e7fb74f8e0e517b566d46d61c316ebe2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796840"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority 接口
提供一些方法，这些方法可为应用程序标识和引用生成和比较键。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|获取一个值，该值指示两个指定的[IDefinitionAppId](idefinitionappid-interface.md)实例是否相等。 可以传递标志值 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 来忽略其各自的版本信息。|  
|`IAppIdAuthority::AreReferencesEqual`|获取一个值，该值指示两个指定的[IReferenceAppId](ireferenceappid-interface.md)实例是否相等。 可以传递标志值 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 来忽略其各自的版本信息。|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|获取一个值，该值指示两个指定的字符串定义是否相等。 可以传递标志值 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 来忽略其各自的版本信息。|  
|`IAppIdAuthority::AreTextualReferencesEqual`|获取一个值，该值指示两个指定的字符串引用是否相等。 可以传递标志值 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 来忽略其各自的版本信息。|  
|`IAppIdAuthority::CreateDefinition`|获取一个接口指针，该指针指向`IDefinitionAppId`表示当前范围内的程序集的新生成的实例。|  
|`IAppIdAuthority::CreateReference`|获取一个接口指针，该指针指向`IReferenceAppId`表示当前范围内的程序集的新创建的。|  
|`IAppIdAuthority::DefinitionToText`|使用指定的标志值获取指定`IDefinitionAppId`的的字符串版本。|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|获取一个值，该值指示指定`IDefinitionAppId` `IReferenceAppId`的是否表示相同的程序集。|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|获取一个值，该值指示指定的定义字符串和引用字符串是否表示相同的程序集。|  
|`IAppIdAuthority::GenerateDefinitionKey`|获取表示指定`IDefinitionAppId`实例的字符串键。|  
|`IAppIdAuthority::GenerateReferenceKey`|获取表示指定`IReferenceAppId`实例的字符串键。|  
|`IAppIdAuthority::HashDefinition`|获取指定`IDefinitionAppId`实例的哈希键。|  
|`IAppIdAuthority::HashReference`|获取指定`IReferenceAppId`实例的哈希键。|  
|`IAppIdAuthority::ReferenceToText`|使用指定的标志值获取指定`IReferenceAppId`的的字符串版本。|  
|`IAppIdAuthority::TextToDefinition`|获取一个接口指针，该`IDefinitionAppId`指针指向表示指定字符串键所引用的程序集的实例。|  
|`IAppIdAuthority::TextToReference`|获取一个接口指针，该`IReferenceAppId`指针指向表示指定字符串键所引用的程序集的实例。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 隔离。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
