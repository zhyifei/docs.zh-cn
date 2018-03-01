---
title: "IAssemblyName::GetName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 681df0b4d6b3d7206954264355afb3ef2628243d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblynamegetname-method"></a>IAssemblyName::GetName 方法
获取此引用的程序集的简单、 非加密名称[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `lpcwBuffer`  
 [在中，out]大小`pwzName`以宽字符为单位，包括 null 终止符字符。  
  
 `pwzName`  
 [out]缓冲区以保存引用程序集的名称。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IAssemblyName 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
