---
title: ICorProfilerCallback::UnmanagedToManagedTransition 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
ms.openlocfilehash: c381d4a85a1e836f1972060c8182dd698bb27550
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870530"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition 方法
通知探查器已发生从非托管代码到托管代码的转换。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>参数  
 `functionId`  
 中正在调用的函数的 ID。  
  
 `reason`  
 中一个[COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md)枚举的值，该值指示是否由于从非托管代码调用托管代码而发生了转换，或是否是由托管函数调用的非托管函数返回。  
  
## <a name="remarks"></a>备注  
 如果 `reason` 的值 COR_PRF_TRANSITION_RETURN 并且 `functionId` 不为 null，则函数 ID 为非托管函数的 ID，并且永远不会使用实时（JIT）编译器编译。 非托管函数有一些与之关联的基本信息，如名称和某些元数据。  
  
 如果 COR_PRF_TRANSITION_CALL `reason` 的值，则可能是被调用的函数（即托管函数）尚未进行 JIT 编译。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
- [ManagedToUnmanagedTransition 方法](icorprofilercallback-managedtounmanagedtransition-method.md)
- [在 C++ 中使用显式 PInvoke（DllImport 特性）](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [使用 C++ 互操作（隐式 PInvoke）](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
