---
title: ICorDebugFunctionBreakpoint 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
ms.openlocfilehash: 6a378e3579ab9ea8d9534a408d0e456373616cad
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213131"
---
# <a name="icordebugfunctionbreakpoint-interface"></a>ICorDebugFunctionBreakpoint 接口

扩展 ICorDebugBreakpoint 接口以支持函数内的断点。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetFunction 方法](icordebugfunctionbreakpoint-getfunction-method.md)|获取一个指向 ICorDebugFunction 的接口指针，该指针引用在其中设置断点的函数。|  
|[GetOffset 方法](icordebugfunctionbreakpoint-getoffset-method.md)|获取函数内断点的偏移量。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](debugging-interfaces.md)
