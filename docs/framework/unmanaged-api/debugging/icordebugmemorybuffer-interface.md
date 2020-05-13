---
title: ICorDebugMemoryBuffer 接口
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 60f3b0c3230c524ca7d308d3cb80e50b0693715d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212329"
---
# <a name="icordebugmemorybuffer-interface"></a>ICorDebugMemoryBuffer 接口
表示内存中缓冲区。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetSize 方法](icordebugmemorybuffer-getsize-method.md)|获取内存缓冲区的大小（以字节为单位）。|  
|[GetStartAddress 方法](icordebugmemorybuffer-getstartaddress-method.md)|获取内存缓冲区的起始地址。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
