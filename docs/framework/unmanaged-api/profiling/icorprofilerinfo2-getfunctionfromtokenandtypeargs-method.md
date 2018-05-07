---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 343cedcf26112f0f2bcc7943ea5ee9f302329a15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 方法
获取`FunctionID`通过使用指定元数据标记，包含类的函数和`ClassID`值的任何类型参数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a>参数  
 `moduleID`  
 [in]函数所在模块的 ID。  
  
 `funcDef`  
 [in]`mdMethodDef`引用该函数的元数据标记。  
  
 `classId`  
 [in]函数的包含类的 ID。  
  
 `cTypeArgs`  
 [in]给定的函数的类型参数的数目。 此值必须为零的非泛型函数。  
  
 `typeArgs`  
 [in]数组`ClassID`值，其中每个是函数的自变量。 值`typeArgs`时可以为 NULL`cTypeArgs`设置为零。  
  
 `pFunctionID`  
 [out]指向的指针`FunctionID`指定函数。  
  
## <a name="remarks"></a>备注  
 调用`GetFunctionFromTokenAndTypeArgs`方法替换`mdMethodRef`元数据，而不是`mdMethodDef`元数据的令牌可以具有不可预知的结果。 调用方应解决`mdMethodRef`到`mdMethodDef`时将其传递。  
  
 如果尚未加载该函数，则调用`GetFunctionFromTokenAndTypeArgs`将导致加载发生，这是一种危险操作在多种上下文中的。 例如，在模块或类型的加载过程中调用此方法在运行时尝试循环加载某些内容导致无限循环。  
  
 一般情况下，使用`GetFunctionFromTokenAndTypeArgs`不建议这样做。 如果探查器感兴趣的特定函数的事件，它们应将存储`ModuleID`和`mdMethodDef`该函数，并使用[icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)以检查是否给定`FunctionID`是所需的函数。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
