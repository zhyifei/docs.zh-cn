---
title: "CreateAssemblyEnum 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyEnum
helpviewer_keywords: CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3719da442b2c2c589772a0bc19cec3efb4e6dace
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum 函数
获取一个指向[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)可以枚举中具有指定的程序集的对象的实例[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a>参数  
 `pEnum`  
 [out]指向包含请求的内存位置`IAssemblyEnum`指针。  
  
 `pUnkReserved`  
 [in]留待将来扩展。 `pUnkReserved`必须是 null 引用。  
  
 `pName`  
 [in]`IAssemblyName`的请求的程序集。 此名称用于筛选在枚举。 它可以为 null 来枚举全局程序集缓存中的所有程序集。  
  
 `dwFlags`  
 [in]修改枚举器的行为的标志。 此参数将包含一位完全从[ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)枚举。  
  
 `pvReserved`  
 [in]留待将来扩展。 `pvReserved`必须是 null 引用。  
  
## <a name="remarks"></a>备注  
 `dwFlags`参数包含一位完全从`ASM_CACHE_FLAGS`枚举。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IAssemblyEnum 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [IAssemblyName 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
