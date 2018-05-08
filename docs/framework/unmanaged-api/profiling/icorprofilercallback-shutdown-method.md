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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83e32b2b69d53772f8a4ebaabe1c025b95d1da47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown 方法
通知探查器应用程序正在关闭。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>备注  
 探查器代码不能安全地调用方法的[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)接口后`Shutdown`调用方法。 对任何调用`ICorProfilerInfo`方法都会导致未定义的行为后`Shutdown`方法返回。 某些不可变事件还是会出现后关闭;探查器应注意发生这种情况时立即返回。  
  
 `Shutdown`将调用方法，仅当所分析的托管应用程序启动为托管代码 （即，托管进程堆栈中的初始帧）。 如果应用程序作为非托管代码已启动，但稍后又跳转到托管代码，从而然后创建的公共语言运行时 (CLR) 实例`Shutdown`将不会调用。 对于这些情况下，探查器应包括在其库`DllMain`例程使用 DLL_PROCESS_DETACH 要释放任何资源并执行其数据，如刷新跟踪，依此类推磁盘清理处理的值。  
  
 一般情况下，探查器必须处理意外关闭。 例如，进程可能会暂停通过 Win32 的`TerminateProcess`方法 （在 Winbase.h 中声明）。 在其他情况下，CLR 将暂停某些托管的线程 （后台线程），而无需为它们提供有序析构消息。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Initialize 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
