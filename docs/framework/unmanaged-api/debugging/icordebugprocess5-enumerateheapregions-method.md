---
title: "ICorDebugProcess5::EnumerateHeapRegions 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeapRegions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1365ed5fd8cf308716b16d78e79a26584bd966c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>ICorDebugProcess5::EnumerateHeapRegions 方法
获取托管堆的内存范围的枚举数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppRegions`  
 [out]指向的地址的指针[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)接口对象，它的对象位于托管堆的内存范围的枚举数。  
  
## <a name="remarks"></a>备注  
 之前调用`ICorDebugProcess5::EnumerateHeapRegions`方法时，应调用[icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法并检查的值的`areGCStructuresValid`字段返回[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)要确保其当前状态中的垃圾回收堆是可枚举对象。 此外，`ICorDebugProcess5::EnumerateHeapRegions`方法返回`E_FAIL`如果附加的进程的生存期内太早，内存区域创建之前。  
  
 此方法可得到保证，可能包含托管的对象的所有内存区域进行枚举，但它无法保障托管的对象实际驻留在这些区域中。 [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)集合对象可能包含空或保留的内存区域。  
  
 [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)接口对象是从使您能够枚举 ICorDebugEnum 接口派生的标准枚举器[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)对象。 每个[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)对象提供了特定分段，以及该片段中的对象的代的内存范围信息。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugProcess5 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
