---
title: "IDefinitionIdentity 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionIdentity
helpviewer_keywords: IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b074ae2a0a4e4e65f0402ff35888b557b00dd071
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity 接口
表示在当前范围内定义应用程序的代码的唯一签名。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|到新获取的接口指针`IDefinitionIdentity`对象，它等同于此`IDefinitionIdentity`，除指定的属性更改外。|  
|`IDefinitionIdentity::EnumAttributes`|获取到的接口指针[IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)对象，其中包含与此关联的特性`IDefinitionIdentity`。|  
|`IDefinitionIdentity::GetAttribute`|获取具有指定名称的属性的值中指定的命名空间。|  
|`IDefinitionIdentity::SetAttribute`|设置为指定的值指定的命名空间中具有指定的名称的属性。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
