---
title: 分析接口
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: adc47417265d32d79508af949c118c4d31a83365
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124199"
---
# <a name="profiling-interfaces"></a>分析接口
本节描述允许对公共语言运行时 (CLR) 正在执行的程序进行分析的非托管接口。  
  
## <a name="in-this-section"></a>本节内容  
 [ICLRProfiling 接口](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 提供[AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)方法，该方法可使探查器附加到正在运行的进程。  
  
 [ICorProfilerAssemblyReferenceProvider 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 启用探查器以通知程序集引用的 CLR，探查器将在[ICorProfilerCallback：： ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调中添加这些引用。  
  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 提供 CLR 在代码探查器订阅的事件发生时用来通知该探查器的方法。  
  
 [ICorProfilerCallback2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 使用 NET Framework 2.0 及更高版本支持的回调扩展 `ICorProfilerCallback` 接口。  
  
 [ICorProfilerCallback3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 提供 CLR 用于将附加和分离状态信息传递给探查器的回调方法。  
  
 [ICorProfilerCallback4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 提供 CLR 用于将信息传递给探查器的回调方法。  
  
 [ICorProfilerCallback5 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 提供用于标识由垃圾回收根引用的对象的传递闭包的方法。  
  
 [ICorProfilerCallback6 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 提供 CLR 用于通知探查器正在加载程序集的回调方法。  
  
 [ICorProfilerCallback7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 提供一个回调方法，公共语言运行时使用该方法通知探查器已更新与内存中模块关联的符号流。  

[ICorProfilerCallback8 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
提供回调方法，公共语言运行时使用该方法通知探查器已开始和完成动态方法的 JIT 编译。

[ICorProfilerCallback9 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
提供一个回调方法，公共语言运行时使用该方法通知探查器动态方法是经过垃圾回收并随后卸载。

 [ICorProfilerFunctionControl 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 提供允许代码探查器与 CLR 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。  
  
 [ICorProfilerFunctionEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 提供按顺序循环访问 CLR 中函数集合的方法。  
  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 提供代码探查器用于与 CLR 通信以控制事件监视及请求信息的方法。  
  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 使用 NET Framework 2.0 及更高版本支持的方法扩展 `ICorProfilerInfo` 接口。  
  
 [ICorProfilerInfo3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 利用 .NET Framework 4 及更高版本中支持的方法扩展 `ICorProfilerInfo2` 接口。  
  
 [ICorProfilerInfo4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 提供一些方法，代码探查器可以使用这些方法与 CLR 通信，从而控制事件监视并请求信息。  
  
 [ICorProfilerInfo5 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 提供代码探查器用于与 CLR 通信以控制事件监视的方法。  
  
 [ICorProfilerInfo6 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 为属于给定的 NGen 模块并在给定方法的主体中内联的所有方法提供一个枚举器。  
  
 [ICorProfilerInfo7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 提供了一种方法，用于将新定义的元数据应用于模块，并提供对内存中符号流的访问。  
  
 [ICorProfilerModuleEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 提供用于按顺序循环访问应用程序或探查器加载的模块集合的方法。  
  
 [ICorProfilerObjectEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 提供按顺序循环访问[ngen.exe （本机映像生成器）](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)生成的冻结对象的集合的方法。  
  
 [ICorProfilerThreadEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 提供按顺序循环访问 CLR 中线程集合的方法。  
  
 [IMethodMalloc 接口](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 为新的 Microsoft 中间语言（MSIL）函数体提供分配内存的[分配](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)方法。  
  
## <a name="related-sections"></a>相关章节  
 [分析概述](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [分析结构](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
