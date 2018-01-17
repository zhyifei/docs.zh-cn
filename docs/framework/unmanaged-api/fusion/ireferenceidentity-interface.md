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
ms.workload: dotnet
ms.openlocfilehash: c9696687f292d7dcaa3d430c1e269f0fedb05e98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumIDENTITY_ATTRIBUTE 接口](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
