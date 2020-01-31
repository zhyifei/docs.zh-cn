---
title: ICorDebugHeapSegmentEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: 98e3351c9c86961d11b0985117259d0ff3b609ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794421"
---
# <a name="icordebugheapsegmentenum-interface"></a>ICorDebugHeapSegmentEnum 接口
提供针对托管堆的内存区域的枚举器。 此接口是 ICorDebugEnum 接口的子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Next 方法](icordebugheapsegmentenum-next-method.md)|获取指定数量的[COR_HEAPOBJECT](cor-heapobject-structure.md)实例，这些实例包含有关托管堆区域的信息。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugHeapSegmentEnum` 接口实现 ICorDebugEnum 接口。  
  
 `ICorDebugHeapSegmentEnum` 实例通过调用[ICorDebugProcess5：： EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md)方法填充[COR_HEAPOBJECT](cor-heapobject-structure.md)实例。 可以通过调用[ICorDebugHeapSegmentEnum：： Next](icordebugheapsegmentenum-next-method.md)方法枚举集合中的[COR_HEAPOBJECT](cor-heapobject-structure.md)对象。  
  
 `ICorDebugHeapSegmentEnum` 集合对象枚举可能包含托管对象的所有内存区域，但不保证托管对象实际驻留在这些区域中。 它可能包括有关空的或保留的内存区域的信息。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
