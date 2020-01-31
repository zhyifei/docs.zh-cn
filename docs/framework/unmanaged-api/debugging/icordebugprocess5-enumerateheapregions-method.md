---
title: ICorDebugProcess5::EnumerateHeapRegions 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
ms.openlocfilehash: 8070b0693b5718ad8b4cbeb9bf5792cb7f4a0a85
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792407"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>ICorDebugProcess5::EnumerateHeapRegions 方法
获取托管堆的内存范围的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppRegions`  
 弄指向[ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)接口对象地址的指针，该对象是对象驻留在托管堆中的内存范围的枚举器。  
  
## <a name="remarks"></a>备注  
 在调用 `ICorDebugProcess5::EnumerateHeapRegions` 方法之前，应调用[ICorDebugProcess5：： GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md)方法，并检查返回的[COR_HEAPINFO](cor-heapinfo-structure.md)对象的 `areGCStructuresValid` 字段的值，以确保其当前状态的垃圾回收堆可枚举。 此外，如果在进程的生存期内附加过早，则在创建内存区域之前，`ICorDebugProcess5::EnumerateHeapRegions` 方法返回 `E_FAIL`。  
  
 此方法保证可以枚举可能包含托管对象的所有内存区域，但不保证托管对象实际驻留在这些区域中。 [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)集合对象可能包含空的或保留的内存区域。  
  
 [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)接口对象是从 ICorDebugEnum 接口派生的标准枚举器，该枚举器可用于枚举[COR_SEGMENT](cor-segment-structure.md)的对象。 每个[COR_SEGMENT](cor-segment-structure.md)对象均提供有关特定段的内存范围以及该段中的对象的生成信息。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugProcess5 接口](icordebugprocess5-interface.md)
- [调试接口](debugging-interfaces.md)
