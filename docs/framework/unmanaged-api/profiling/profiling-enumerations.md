---
title: 分析枚举
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: bc90743fb348c31bd2f7487c1573ec38a43bd3af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447445"
---
# <a name="profiling-enumerations"></a>分析枚举
本节描述分析 API 使用的非托管枚举。  
  
## <a name="in-this-section"></a>本节内容  
 [COR_PRF_CLAUSE_TYPE 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 指示代码刚进入或离开的异常子句的类型。  
  
 [COR_PRF_CODEGEN_FLAGS 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.  
  
 [COR_PRF_FINALIZER_FLAGS 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 描述对象的终结器。  
  
 [COR_PRF_GC_GENERATION 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 标识垃圾回收生成。  
  
 [COR_PRF_GC_REASON 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 指示当前发生垃圾回收的原因。  
  
 [COR_PRF_GC_ROOT_FLAGS 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 指示垃圾回收器根的属性。  
  
 [COR_PRF_GC_ROOT_KIND 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.  
  
 [COR_PRF_HIGH_MONITOR 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.  
  
 [COR_PRF_JIT_CACHE 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 指示缓存的函数搜索的结果。  
  
 [COR_PRF_MISC 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 包含指定特殊标识符的常数值。  
  
 [COR_PRF_MODULE_FLAGS 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 指定模块的属性。  
  
 [COR_PRF_MONITOR 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 包含用于指定探查器希望订阅的行为、功能或事件的值。  
  
 [COR_PRF_RUNTIME_TYPE 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 包含指示公共语言运行时的版本的值。  
  
 [COR_PRF_SNAPSHOT_INFO 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 指定在每次调用探查器的 `StackSnapshotCallback` 函数时通过堆栈快照传回多少数据。  
  
 [COR_PRF_STATIC_TYPE 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 指示字段是否为静态的，并在字段为静态字段时指示应用于该字段的静态质量。  
  
 [COR_PRF_SUSPEND_REASON 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 指示运行时挂起的原因。  
  
 [COR_PRF_TRANSITION_REASON 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 指示从托管代码向非托管代码转换或从非托管代码向托管代码转换的原因。  
  
## <a name="related-sections"></a>相关章节  
 [分析概述](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [分析结构](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
