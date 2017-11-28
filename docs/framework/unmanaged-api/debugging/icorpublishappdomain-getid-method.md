---
title: "ICorPublishAppDomain::GetID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomain.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbde806f409f2639b2468e0ba962b1659d1ffc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomaingetid-method"></a>ICorPublishAppDomain::GetID 方法
获取此唯一标识符[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `puId`  
 [out]指向应用程序域的标识符的指针。  
  
## <a name="remarks"></a>备注  
 仅在包含进程的作用域中的标识符是唯一的。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub.idl、 CorPub.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorPublishAppDomain 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
