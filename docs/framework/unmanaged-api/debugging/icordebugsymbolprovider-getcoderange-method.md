---
title: "ICorDebugSymbolProvider::GetCodeRange 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c46fb62e5f1867e2b527404bd3d003ba884ebfbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a>ICorDebugSymbolProvider::GetCodeRange 方法
给定方法的相对虚拟地址 (RVA)，获取该方法的起始地址和大小。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `codeRva`  
 [in] 方法中的相对虚拟地址 (RVA)。  
  
 `pCodeStartAddress`  
 [out] 指向该方法的起始地址的指针。  
  
 `pCodeSize`  
 指向方法代码大小（该方法的代码的字节数）的指针。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugSymbolProvider 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
