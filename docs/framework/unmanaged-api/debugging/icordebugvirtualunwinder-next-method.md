---
title: ICorDebugVirtualUnwinder::Next 方法
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6b6b7078db058150ec39bcf82e6984a1949e7cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507130"
---
# <a name="icordebugvirtualunwindernext-method"></a>ICorDebugVirtualUnwinder::Next 方法
前进到调用方的上下文。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Next();  
```  
  
#### <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 如果成功展开，则为 `S_OK`如果因帧不够而无法完全展开，则为 `CORDBG_S_AT_END_OF_STACK`。  
  
 如果返回失败的 HRESULT，则 ICorDebug API 将返回 `CORDBG_E_DATA_TARGET_ERROR`。  
  
## <a name="remarks"></a>备注  
 堆栈查看器应确保向前推进，以便最后 `Next` 的调用将返回失败的 HRESULT 或 `CORDBG_S_AT_END_OF_STACK`。 返回`S_OK`无限期可能会导致无限循环。  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorDebugMemoryBuffer 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
