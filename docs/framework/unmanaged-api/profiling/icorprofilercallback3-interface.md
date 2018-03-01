---
title: "ICorProfilerCallback3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1419dfff7005b33fd1f8a545d168a410e7a88a76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback3-interface"></a>ICorProfilerCallback3 接口
提供公共语言运行时 (CLR) 用于通信的回叫方法附加和分离探查器的状态信息。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[InitializeForAttach 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|由 CLR 使探查器可以将其状态初始化附加操作后调用。|  
|[ProfilerAttachComplete 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|由 CLR 以指示探查器现在可以调用追赶方法调用。|  
|[ProfilerDetachSucceeded 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|通知探查器公共语言运行时 (CLR) 将要卸载探查器 DLL。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerCallback2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [ICorProfilerCallback4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
