---
title: "分析接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
caps.latest.revision: "31"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c0423f9c8b01c1289e1107c0c16c59968a6e2a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-interfaces"></a>分析接口
本节描述允许对公共语言运行时 (CLR) 正在执行的程序进行分析的非托管接口。  
  
## <a name="in-this-section"></a>本节内容  
 [ICLRProfiling 接口](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 提供[AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)方法，使探查器附加到正在运行的进程。  
  
 [Icorprofilerassemblyreferenceprovider 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 探查器能够通知探查器将在中添加的程序集引用的 CLR [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。  
  
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
 提供公共语言运行时用于通知探查器已更新与内存中模块关联的符号流的回调方法。  
  
 [ICorProfilerFunctionControl 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 提供允许代码探查器与 CLR 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。  
  
 [ICorProfilerFunctionEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 提供按顺序循环访问 CLR 中函数集合的方法。  
  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 提供代码探查器用于与 CLR 通信以控制事件监视及请求信息的方法。  
  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 使用 NET Framework 2.0 及更高版本支持的方法扩展 `ICorProfilerInfo` 接口。  
  
 [ICorProfilerInfo3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 使用 `ICorProfilerInfo2` 及更高版本支持的方法扩展 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 接口。  
  
 [ICorProfilerInfo4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 提供一些方法，代码探查器可以使用这些方法与 CLR 通信，从而控制事件监视并请求信息。  
  
 [ICorProfilerInfo5 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 提供代码探查器用于与 CLR 通信以控制事件监视的方法。  
  
 [ICorProfilerInfo6 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 提供对属于给定 NGen 模块以及在给定方法的正文中内联的所有方法的枚举器。  
  
 [ICorProfilerInfo7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 提供方法以应用新模块定义元数据和使您可以访问的内存中的符号流。  
  
 [ICorProfilerModuleEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 提供用于按顺序循环访问应用程序或探查器加载的模块集合的方法。  
  
 [ICorProfilerObjectEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 提供按顺序循环访问集合的冻结对象生成的方法[Ngen.exe （本机映像生成器）](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)。  
  
 [ICorProfilerThreadEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 提供按顺序循环访问 CLR 中线程集合的方法。  
  
 [IMethodMalloc 接口](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 提供[Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)方法来为新的 Microsoft 中间语言 (MSIL) 函数主体分配内存。  
  
## <a name="related-sections"></a>相关章节  
 [分析概述](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [分析结构](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
