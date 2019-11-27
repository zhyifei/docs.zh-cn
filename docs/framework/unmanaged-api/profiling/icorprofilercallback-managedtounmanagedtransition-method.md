---
title: ICorProfilerCallback::ManagedToUnmanagedTransition 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
ms.openlocfilehash: f4f5871bdd7adf11fcc811fd40c62e3027b8e607
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426184"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>ICorProfilerCallback::ManagedToUnmanagedTransition 方法
通知探查器已发生从托管代码到非托管代码的转换。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>参数  
 `functionId`  
 中正在调用的函数的 ID。  
  
 `reason`  
 中一个[COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)枚举的值，该值指示是否由于从托管代码调用非托管代码而发生转换，或者是否是由非托管函数调用的托管函数返回。  
  
## <a name="remarks"></a>备注  
 如果 `reason` 的值 COR_PRF_TRANSITION_CALL，则函数 ID 就是非托管函数的 ID，该函数永远不会使用实时编译器进行编译。 非托管函数具有与之关联的基本信息，如名称和某些元数据。 如果使用隐式平台调用（PInvoke）调用了非托管函数，则运行时无法确定调用的目标，并且 `functionId` 的值将为 null。 有关隐式 PInvoke 的详细信息，请参阅[ C++ Using 互操作（隐式 pinvoke）](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [UnmanagedToManagedTransition 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [在 C++ 中使用显式 PInvoke（DllImport 特性）](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
