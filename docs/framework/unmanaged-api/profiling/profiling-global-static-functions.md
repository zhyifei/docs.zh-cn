---
title: 分析全局静态函数
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bb5d93c91de857ebbee63009cad73fba7e1d284
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758244"
---
# <a name="profiling-global-static-functions"></a>分析全局静态函数
本节描述分析 API 使用的非托管的 API 函数。  
  
## <a name="in-this-section"></a>本节内容  
  
## <a name="net-framework-version-1-profiling-functions"></a>.NET framework 版本 1 分析函数  
 [FunctionEnter 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 通知探查器控件传递给函数。 .NET Framework 2.0 中已弃用。  
  
 [FunctionLeave 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 通知探查器函数以返回到调用方。 .NET Framework 2.0 中已弃用。  
  
 [FunctionTailcall 函数](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 通知探查器当前正在执行的函数将要执行到另一个函数的结尾调用。 .NET Framework 2.0 中已弃用。  
  
## <a name="net-framework-version-2-profiling-functions"></a>.NET framework 版本 2 分析函数  
 [FunctionIDMapper 函数](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)， [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)，和[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)该函数的回调。 此外使探查器以指示它是否想要为该函数接收回调  
  
 [FunctionEnter2 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 通知探查器，控制被传递给函数，并介绍有关堆栈帧和函数参数。 中已弃用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [FunctionLeave2 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 函数即将返回给调用方，并提供有关堆栈帧和函数返回值的信息，请通知探查器。 中已弃用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [FunctionTailcall2 函数](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 通知探查器当前正在执行的函数将要执行到另一个函数的结尾调用并提供有关堆栈帧的信息。 中已弃用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StackSnapshotCallback 函数](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 提供有关每个托管的帧和非托管帧的每次运行在堆栈上的堆栈遍历，启动的过程信息，以及探查器[ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法。  
  
## <a name="net-framework-version-4-profiling-functions"></a>.NET framework 版本 4 分析函数  
 [FunctionIDMapper2 函数](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)， [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)，和[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)，或[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，并且[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)该函数的回调。 此外使探查器以指示它是否想要接收该函数的回调。  
  
 `FunctionIDMapper2` 扩展了[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)函数与`clientData`探查器可能用于消除运行时间歧义的参数。  
  
 [FunctionEnter3 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 通知探查器控件传递给函数。  
  
 [FunctionEnter3WithInfo 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 通知探查器正在将控件传递给函数，并提供句柄，可传递给[ICorProfilerInfo3::GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)以检索堆栈帧和函数参数。  
  
 [FunctionLeave3 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 通知探查器从函数返回控制。  
  
 [FunctionLeave3WithInfo 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 通知探查器一个函数，从正在返回控制和提供句柄，可传递给[ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)检索堆栈帧和返回值。  
  
 [FunctionTailcall3 函数](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 通知探查器当前正在执行的函数将要执行到另一个函数的结尾调用。  
  
 [FunctionTailcall3WithInfo 函数](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 通知当前正在执行的函数将执行到另一个函数的结尾调用探查器和提供句柄，可传递给[ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)检索堆栈帧。  
  
## <a name="related-sections"></a>相关章节  
 [分析概述](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [分析结构](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
