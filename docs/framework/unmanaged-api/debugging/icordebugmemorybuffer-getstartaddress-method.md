---
title: ICorDebugMemoryBuffer::GetStartAddress 方法
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 47369c744ee42fb03857a3e69063a04e4f509d0d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212342"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a>ICorDebugMemoryBuffer::GetStartAddress 方法
获取内存缓冲区的起始地址。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a>参数  
 `address`  
 [out] 指向内存缓冲区起始地址的指针。  
  
## <a name="remarks"></a>备注  
  
> [!WARNING]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugMemoryBuffer 接口](icordebugmemorybuffer-interface.md)
- [调试接口](debugging-interfaces.md)
