---
title: "ICorDebugGCReferenceEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGCReferenceEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGCReferenceEnum
helpviewer_keywords: ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1afe52c3df8f61b234b3c68ee819ba8389593c82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum 接口
提供针对将进行垃圾回收的对象的枚举器。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Next 方法](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|获取指定的数目的[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)包含有关将进行垃圾回收的对象的信息的实例。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugGCReferenceEnum`接口实现"ICorDebugEnum"接口。  
  
 `ICorDebugGCReferenceEnum`实例填入[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)实例通过调用[icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法。 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)对象可以通过调用枚举[ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)方法。  
  
 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)填充此方法对集合中的对象表示三种类型的对象：  
  
-   从所有托管堆栈的对象。 这包括实时引用中托管的代码，以及由公共语言运行时创建的对象。  
  
-   来自句柄表的对象。 这包括的强引用 (`HNDTYPE_STRONG`和`HNDTYPE_REFCOUNT`) 和模块中的静态变量。  
  
-   终结器队列中的对象。 终结器队列根对象，直到运行终结器。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
