---
title: "ICorProfilerCallback3::ProfilerAttachComplete 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerAttachComplete Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1472658fb5d2d68b14574b233bd5950d0a7abe5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a>ICorProfilerCallback3::ProfilerAttachComplete 方法
由公共语言运行时 (CLR) 以指示探查器现在可以调用调用[icorprofilerinfo3:: Enumjitedfunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)和[icorprofilerinfo3:: Enummodules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)追赶方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a>备注  
 `ProfilerAttachComplete`回调后将发出[icorprofilercallback3:: Initializeforattach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)调用方法。 指示如下内容：  
  
-   已激活 `InitializeForAttach` 中的探测器请求的回调。  
  
-   探查器现在可以对关联的 ID 执行追赶操作，而不必担心丢失通知。  
  
 CLR 将忽略从此回调返回的值。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerInfo3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
