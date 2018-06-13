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
ms.openlocfilehash: 819afec2c448e5f396ab54e2dde00c01da310b12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433745"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority 接口
提供用于生成并比较应用程序标识和引用的密钥的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|获取一个值，该值指示两个指定[IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)实例是否相等。 你可以将传递 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 若要忽略及其各自的版本信息的标志值。|  
|`IAppIdAuthority::AreReferencesEqual`|获取一个值，该值指示两个指定[IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)实例是否相等。 你可以将传递 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 若要忽略及其各自的版本信息的标志值。|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|获取一个值，该值指示两个指定的字符串定义是否相等。 你可以将传递 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 若要忽略及其各自的版本信息的标志值。|  
|`IAppIdAuthority::AreTextualReferencesEqual`|获取一个值，该值指示两个指定的字符串引用是否相等。 你可以将传递 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 若要忽略及其各自的版本信息的标志值。|  
|`IAppIdAuthority::CreateDefinition`|获取新生成的接口指针`IDefinitionAppId`表示当前范围中的程序集的实例。|  
|`IAppIdAuthority::CreateReference`|获取新创建的接口指针`IReferenceAppId`，它表示当前范围中的程序集。|  
|`IAppIdAuthority::DefinitionToText`|获取指定的字符串版本`IDefinitionAppId`，使用指定的标志值。|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|获取一个值，该值指示是否指定`IDefinitionAppId`和`IReferenceAppId`表示相同的程序集。|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|获取一个值，该值指示指定的定义字符串和引用字符串是否表示相同的程序集。|  
|`IAppIdAuthority::GenerateDefinitionKey`|获取一个表示指定的字符串键`IDefinitionAppId`实例。|  
|`IAppIdAuthority::GenerateReferenceKey`|获取一个表示指定的字符串键`IReferenceAppId`实例。|  
|`IAppIdAuthority::HashDefinition`|获取指定的哈希键`IDefinitionAppId`实例。|  
|`IAppIdAuthority::HashReference`|获取指定的哈希键`IReferenceAppId`实例。|  
|`IAppIdAuthority::ReferenceToText`|获取指定的字符串版本`IReferenceAppId`，使用指定的标志值。|  
|`IAppIdAuthority::TextToDefinition`|获取到的接口指针`IDefinitionAppId`表示由指定的字符串参数引用的程序集的实例。|  
|`IAppIdAuthority::TextToReference`|获取到的接口指针`IReferenceAppId`表示由指定的字符串参数引用的程序集的实例。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
