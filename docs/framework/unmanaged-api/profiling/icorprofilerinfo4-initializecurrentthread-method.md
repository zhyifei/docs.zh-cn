---
title: ICorProfilerInfo4::InitializeCurrentThread 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
ms.openlocfilehash: b52a0e7f993629c1005883723c734996d75300a7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868429"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread 方法
在同一线程上的后续探查器 API 调用之前初始化当前线程，以便避免死锁。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>备注  
 建议在存在挂起的线程时，对将调用探查器 API 的任何线程调用 `InitializeCurrentThread`。 此方法通常由创建自己的线程的探查器使用，用来调用[ICorProfilerInfo2：:D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md)方法，在目标线程挂起时执行堆栈遍历。 通过在探查器首次创建采样线程时调用 `InitializeCurrentThread` 一次，探查器可以确保在第一次调用 `DoStackSnapshot` 时，CLR 将以其他方式执行的延迟的每个线程初始化，而不会挂起其他线程。  
  
> [!NOTE]
> `InitializeCurrentThread` 会提前执行初始化来完成接受锁定的任务，并可能导致死锁。 仅当没有挂起的线程时才调用 `InitializeCurrentThread`。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo4 接口](icorprofilerinfo4-interface.md)
- [Profiling 接口](profiling-interfaces.md)
- [分析](index.md)
