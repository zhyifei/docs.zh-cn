---
title: ICorDebugMemoryBuffer::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0db104dbfa61b836aa01b99be45725ed4c04c798
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752789"
---
# <a name="icordebugmemorybuffergetsize-method"></a>ICorDebugMemoryBuffer::GetSize 方法
获取内存缓冲区的大小（以字节为单位）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a>参数  
 `pcbBufferLength`  
 [out] 指向内存缓冲区大小的指针。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugMemoryBuffer 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
