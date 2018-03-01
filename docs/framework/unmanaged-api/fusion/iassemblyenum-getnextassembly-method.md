---
title: "IAssemblyEnum::GetNextAssembly 方法"
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
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2666970e220334e9e8c2470622026442db0c2f95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyenumgetnextassembly-method"></a>IAssemblyEnum::GetNextAssembly 方法
获取一个指针指向下一步[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)包含在此[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pvReserved`  
 [in]留待将来扩展。 `pvReserved`必须是 null 引用。  
  
 `ppName`  
 [out]返回`IAssemblyName`指针。  
  
 `dwFlags`  
 [in]留待将来扩展。 `dwFlags`必须为 0 （零）。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IAssemblyName 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [IAssemblyEnum 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
