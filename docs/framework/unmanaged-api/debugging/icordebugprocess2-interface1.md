---
title: ICorDebugProcess2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
ms.openlocfilehash: 1a57b7ceb6da961fba1f0d6e8e0ba1aa88ca0541
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213486"
---
# <a name="icordebugprocess2-interface"></a>ICorDebugProcess2 接口
ICorDebugProcess 接口的逻辑扩展，它表示运行托管代码的进程。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint 方法](icordebugprocess2-clearunmanagedbreakpoint-method.md)|删除由之前对的调用所设置的指定偏移量处的断点 `ICorDebugProcess2::SetUnmanagedBreakpoint` 。|  
|[GetDesiredNGENCompilerFlags 方法](icordebugprocess2-getdesiredngencompilerflags-method.md)|获取必须为公共语言运行时（CLR）设置的标志，以将图像加载到此所引用的进程中 `ICorDebugProcess2` 。|  
|[GetReferenceValueFromGCHandle 方法](icordebugprocess2-getreferencevaluefromgchandle-method.md)|获取指向具有垃圾回收句柄的指定托管对象的引用指针。|  
|[GetThreadForTaskID 方法](icordebugprocess2-getthreadfortaskid-method.md)|获取执行具有指定标识符的任务的线程。|  
|[GetVersion 方法](icordebugprocess2-getversion-method.md)|获取正在运行正在调试的进程的 CLR 的版本。|  
|[SetDesiredNGENCompilerFlags 方法](icordebugprocess2-setdesiredngencompilerflags-method.md)|将实时（JIT）编译器所需的标志设置为将图像加载到正在调试的进程中。|  
|[SetUnmanagedBreakpoint 方法](icordebugprocess2-setunmanagedbreakpoint-method.md)|在指定的本机映像偏移量处设置非托管断点。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](debugging-interfaces.md)
