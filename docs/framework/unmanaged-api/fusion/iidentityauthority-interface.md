---
title: "IIdentityAuthority 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IIdentityAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IIdentityAuthority
helpviewer_keywords: IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 322b15252271472b5bee1dfc6a843079cebbe0b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority 接口
管理代码对象的标识键。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|获取一个值，该值指示两个指定[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)实例是否相等。|  
|`IIdentityAuthority::AreReferencesEqual`|获取一个值，该值指示两个指定[IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)实例是否相等。|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|获取一个值，该值指示两个指定的字符串定义标识的表示形式是否相等。|  
|`IIdentityAuthority::AreTextualReferencesEqual`|获取一个值，该值指示两个指定的字符串引用标识的表示形式是否相等。|  
|`IIdentityAuthority::CreateDefinition`|获取一个指针，到新`IDefinitionIdentity`表示当前范围中的代码对象的实例。|  
|`IIdentityAuthority::CreateReference`|获取一个指针，到新`IReferenceIdentity`表示当前范围中的代码对象的实例。|  
|`IIdentityAuthority::DefinitionToText`|获取指定的格式化的字符串版本`IDefinitionIdentity`。|  
|`IIdentityAuthority::DefinitionToTextBuffer`|用指定的字符串版本填充指定的宽字符缓冲区`IDefinitionIdentity`。|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|获取一个值，该值指示是否指定`IDefinitionIdentity`和`IReferenceIdentity`实例引用相同的代码对象。|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|获取一个值，该值指示指定的字符串是否引用相同的代码对象。|  
|`IIdentityAuthority::GenerateDefinitionKey`|获取一个指针指向新创建的字符串键指定`IDefinitionIdentity`。|  
|`IIdentityAuthority::GenerateReferenceKey`|获取一个指针指向新创建的字符串键指定`IReferenceIdentity`。|  
|`IIdentityAuthority::HashDefinition`|获取指定的哈希值`IDefinitionIdentity`。|  
|`IIdentityAuthority::HashReference`|获取指定的哈希值`IreferenceIdentity`。|  
|`IIdentityAuthority::ReferenceToText`|获取指定的格式化的字符串版本`IReferenceIdentity`。|  
|`IIdentityAuthority::ReferenceToTextBuffer`|用指定的字符串版本填充指定的宽字符缓冲区`IReferenceIdentity`。|  
|`IIdentityAuthority::TextToDefinition`|获取到的接口指针`IDefinitionIdentity`实例生成从指定格式字符串。|  
|`IIdentityAuthority::TextToReference`|获取到的接口指针`IReferenceIdentity`实例生成从指定格式字符串。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
