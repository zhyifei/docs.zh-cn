---
title: ICorDebugHeapValue2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2
helpviewer_keywords:
- ICorDebugHeapValue2 interface [.NET Framework debugging]
ms.assetid: 87360a52-90b1-4ada-80c0-589a556116d8
topic_type:
- apiref
ms.openlocfilehash: bf9b0b7a9bcd09d6e4b3a2cecac1f1b1e711b6bb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213772"
---
# <a name="icordebugheapvalue2-interface"></a>ICorDebugHeapValue2 接口

为公共语言运行时（CLR）句柄提供支持的 ICorDebugHeapValue 扩展。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateHandle 方法](icordebugheapvalue2-createhandle-method.md)|为此对象创建指定类型的句柄 `ICorDebugHeapValue2` 。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](debugging-interfaces.md)
