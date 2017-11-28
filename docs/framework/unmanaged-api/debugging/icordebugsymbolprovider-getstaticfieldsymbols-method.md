---
title: "ICorDebugSymbolProvider::GetStaticFieldSymbols 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a6741adcc30d3dffee79e909db4334db66eb049
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a>ICorDebugSymbolProvider::GetStaticFieldSymbols 方法
获取与 Typespec 签名相对应的静态字段符号。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cbSignature`  
 [in] `typeSig` 数组中的字节数。  
  
 `typeSig`  
 [in] 包含 `typespec` 签名的字节数组。  
  
 `cRequestedSymbols`  
 [in] 请求的符号数。  
  
 `pcFetchedSymbols`  
 [out] 一个指针，指向由方法检索的符号的数量。  
  
 `pSymbols`  
 [out]指向的指针[ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)数组，其中包含请求的静态字段符号。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [GetInstanceFieldSymbols 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)  
 [ICorDebugSymbolProvider 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
