---
title: "调试结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0293a20f5f735dd38b1d167ebc5057f645fa011a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-structures"></a>调试结构
本节描述调试 API 使用的非托管结构。  
  
## <a name="in-this-section"></a>本节内容  
 [CLR_DEBUGGING_VERSION 结构](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 出于调试目的，定义公共语言运行时 (CLR) 的产品版本。  
  
 [CodeChunkInfo 结构 1](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 表示内存中的单一代码块。  
  
 [CorDebugBlockingObject 结构](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 定义一个阻塞线程的对象以及阻塞线程的原因。  
  
 [CorDebugEHClause 结构](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 表示给定的一段中间语言 (IL) 的异常处理 (EH) 子句。  
  
 [CorDebugExceptionObjectStackFrame 结构](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 表示异常对象中的堆栈帧信息。  
  
 [CorDebugExceptionObjectStackFrame 结构](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 地图[!INCLUDE[wrt](../../../../includes/wrt-md.md)]到其对应的 GUID [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)对象。  
  
 COR_ACTIVE_FUNCTION  
 包含有关在线程框架中当前处于活动状态的函数的信息。  
  
 [COR_ARRAY_LAYOUT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 提供有关内存中数组对象的布局的信息。  
  
 COR_DEBUG_IL_TO_NATIVE_MAP  
 包含用于将 Microsoft 中间语言 (MSIL) 代码映射到本机代码的偏移量。  
  
 COR_DEBUG_STEP_RANGE  
 包含代码区域的偏离量信息。  
  
 [COR_FIELD 结构](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 提供有关对象中的某个字段的信息。  
  
 [COR_GC_REFERENCE 结构](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 包含有关要进行垃圾回收的对象的信息。  
  
 [COR_HEAPINFO 结构](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 提供有关垃圾回收堆的常规信息，包括它是否是可枚举的。  
  
 [COR_HEAPOBJECT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 提供有关托管堆上的对象的信息。  
  
 COR_IL_MAP  
 指定函数的相对偏移量的更改。  
  
 [COR_SEGMENT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 包含有关托管堆中的内存区域的信息。  
  
 [COR_TYPEID 结构](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 包含类型标识符。  
  
 [COR_TYPE_LAYOUT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 提供有关内存中某个对象的布局的信息。  
  
 COR_VERSION  
 存储由四个部分组成的公共语言运行时标准版本号。  
  
 [StackTrace_SimpleContext 结构](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 提供可用于代替完整的 `CONTEXT` 结构的简单上下文。  
  
## <a name="related-sections"></a>相关章节  
 [调试组件类](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [调试全局静态函数](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
