---
title: "ICorProfilerModuleEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum
api_location: mscorwks.cll
api_type: COM
f1_keywords: ICorProfilerModuleEnum
helpviewer_keywords: ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 43cc6afc42fc1a02fd7d7b3df2973cc9b3e31251
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenum-interface"></a>ICorProfilerModuleEnum 接口
提供用于按顺序循环访问应用程序或探查器加载的模块集合的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Clone 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|获取指向此 `ICorProfilerModuleEnum` 接口副本的接口指针。|  
|[GetCount 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|获取已加载到应用程序的托管模块数。|  
|[Next 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|从对象的序列集合中获取指定的连续模块数，从该序列中的枚举器当前位置开始。|  
|[Reset 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|将枚举器的光标移动到序列的起始位置。|  
|[Skip 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|前移枚举器的光标位置，以便跳过指定的元素数。|  
  
## <a name="remarks"></a>备注  
 `ICorProfilerModuleEnum` 接口是一个枚举器。 它可以让数组接收器以其合适的速率从发送器提取元素。 换而言之，接收器可以显式控制数组元素流，从而避免将大型数组作为方法形参传递方面的相关问题。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [分析接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumModules 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
