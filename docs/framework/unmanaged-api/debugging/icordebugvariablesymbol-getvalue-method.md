---
title: ICorDebugVariableSymbol::GetValue 方法
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b72b9dbeff6aa06a132dc7ec3ddd9477553c4c2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967992"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>ICorDebugVariableSymbol::GetValue 方法
获取作为字节数组的变量的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `offset`  
 [in] 从其读取值的变量中的起始偏移量。 读取对象中的成员字段时使用此参数。  
  
 `cbContext`  
 [in] `context` 参数的大小（以字节为单位）。  
  
 `context`  
 [in] 用于读取值的线程上下文。  
  
 `cbValue`  
 [in] `pValue` 缓冲区的大小（以字节为单位）。  
  
 `pcbValue`  
 [out] 实际写入 `pValue` 缓冲区的字节数。  
  
 `pValue`  
 [out] 包含变量值的字节数组。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugVariableSymbol 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
