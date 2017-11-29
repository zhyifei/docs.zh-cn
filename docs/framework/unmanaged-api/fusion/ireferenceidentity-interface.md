---
title: "IReferenceIdentity 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceIdentity
helpviewer_keywords: IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35c6152836adf02d541bacd149ed9ac053765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity 接口
表示对代码对象的唯一签名的引用。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|到新获取的接口指针`IReferenceIdentity`是否与此实例`IReferenceIdentity`，除指定的属性更改外。|  
|`IReferenceIdentity::EnumAttributes`|获取到的接口指针`IEnumIDENTITY_ATTRIBUTE`实例，其中包含与此关联的特性`IReferenceIdentity`。|  
|`IReferenceIdentity::GetAttribute`|获取属性的值中指定的命名空间，具有指定名称。|  
|`IReferenceIdentity::SetAttribute`|设置具有指定的命名空间和指定的名称与指定的值的属性。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumIDENTITY_ATTRIBUTE 接口](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
