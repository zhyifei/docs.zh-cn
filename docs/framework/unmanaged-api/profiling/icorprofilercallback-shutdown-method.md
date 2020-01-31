---
title: ICorProfilerCallback::Shutdown 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 490f9dd5446a51bd07881cdb9825d737e380a63e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865852"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown 方法
通知探查器应用程序正在关闭。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>备注  
 调用 `Shutdown` 方法之后，探查器代码将无法安全地调用[ICorProfilerInfo](icorprofilerinfo-interface.md)接口的方法。 调用 `ICorProfilerInfo` 方法会导致在 `Shutdown` 方法返回后出现未定义的行为。 某些不可变事件可能仍会在关闭后发生;此事件发生时，探查器应小心立即返回。  
  
 仅当要分析的托管应用程序作为托管代码启动时（即，处理堆栈上的初始帧是托管的），将调用 `Shutdown` 方法。 如果应用程序启动为非托管代码，但后来跳转到托管代码，从而创建公共语言运行时（CLR）的实例，则不会调用 `Shutdown`。 对于这些情况，探查器应在其库中包含一个 `DllMain` 例程，该例程使用 DLL_PROCESS_DETACH 值来释放所有资源并对其数据执行清理处理，如将跟踪刷新到磁盘等。  
  
 通常，探查器必须处理意外关闭。 例如，进程可能由 Win32 `TerminateProcess` 方法（在 Winbase.h 中声明）暂停。 在其他情况下，CLR 将暂停某些托管线程（后台线程），而无需为它们传递有序的析构消息。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
- [Initialize 方法](icorprofilercallback-initialize-method.md)
