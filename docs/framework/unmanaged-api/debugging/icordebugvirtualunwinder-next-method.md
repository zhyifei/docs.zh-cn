---
title: ICorDebugVirtualUnwinder::Next 方法
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: 06d5377ef123cc3f9c91fbfbcf0b0f17a14eb629
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790820"
---
# <a name="icordebugvirtualunwindernext-method"></a>ICorDebugVirtualUnwinder::Next 方法
前进到调用方的上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 如果成功展开，则为 `S_OK`如果因帧不够而无法完全展开，则为 `CORDBG_S_AT_END_OF_STACK`。  
  
 如果返回失败的 HRESULT，则 ICorDebug API 将返回 `CORDBG_E_DATA_TARGET_ERROR`。  
  
## <a name="remarks"></a>备注  
 堆栈查看器应确保向前推进，以便最后 `Next` 的调用将返回失败的 HRESULT 或 `CORDBG_S_AT_END_OF_STACK`。 无限期返回 `S_OK` 可能导致无限循环。  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugMemoryBuffer 接口](icordebugmemorybuffer-interface.md)
- [调试接口](debugging-interfaces.md)
