---
title: "ICorProfilerCallback::JITCachedFunctionSearchStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2208a1a1637b3bb8dd7d7963ab806aeae7921dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted 方法
通知探查器以前使用本机映像生成器 (NGen.exe) 编译的函数已开始搜索。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a>参数  
 `functionId`  
 [in]为其执行搜索的函数 ID。  
  
 `pbUseCachedFunction`  
 [out]`true`如果执行引擎应使用缓存的版本的函数 （如果可用）; 否则为`false`。 如果值为`false`，执行引擎 JIT 编译的函数而不是使用不是 JIT 编译的版本。  
  
## <a name="remarks"></a>备注  
 在.NET Framework 2.0 版中，`JITCachedFunctionSearchStarted`和[icorprofilercallback:: Jitcachedfunctionsearchfinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)回调将不会执行常规 NGen 映像中的所有功能。 仅为配置文件优化的 NGen 映像将映像中生成的所有函数的回调。 但是，由于的额外开销，探查器应请求探查器优化 NGen 映像仅当它想使用这些回调来强制对函数进行编译的实时 (JIT)。 否则，探查器应使用迟缓策略来收集函数信息。  
  
 探查器必须支持的分析的应用程序的多个线程同时调用同一方法的情况。 例如，调用线程 A`JITCachedFunctionSearchStarted`和探查器响应通过设置*pbUseCachedFunction*为 FALSE 可强制 JIT 编译。 随后将调用的线程[icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)和[icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)。  
  
 现在，线程 B 调用`JITCachedFunctionSearchStarted`同一函数的。 即使探查器已声明其意图对 JIT 编译的函数，在探查器接收第二个回调，因为线程 B 之前探查器已响应线程的调用会将发送回调`JITCachedFunctionSearchStarted`。 在其中线程进行调用的顺序取决于所计划的线程的方式。  
  
 在探查器收到重复的回调，它必须由引用的值会设置`pbUseCachedFunction`为相同的值的所有重复的回调。 也就是说，当`JITCachedFunctionSearchStarted`多次调用了具有相同`functionId`值，探查器必须响应相同每次。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
