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
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433208"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 方法
使用指定的元数据标记（包含类）和任何类型参数 `ClassID` 值获取函数的 `FunctionID`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a>参数  
 `moduleID`  
 中函数所在模块的 ID。  
  
 `funcDef`  
 中引用函数的 `mdMethodDef` 元数据标记。  
  
 `classId`  
 中函数的包含类的 ID。  
  
 `cTypeArgs`  
 中给定函数的类型参数的数目。 对于非泛型函数，此值必须为零。  
  
 `typeArgs`  
 中`ClassID` 值的数组，其中每个值都是函数的参数。 如果 `cTypeArgs` 设置为零，则 `typeArgs` 的值可以为 NULL。  
  
 `pFunctionID`  
 弄指向指定函数的 `FunctionID` 的指针。  
  
## <a name="remarks"></a>备注  
 使用 `mdMethodRef` 元数据而不是 `mdMethodDef` 元数据令牌调用 `GetFunctionFromTokenAndTypeArgs` 方法可能会产生不可预知的结果。 调用方应在传递时将 `mdMethodRef` 解析为 `mdMethodDef`。  
  
 如果尚未加载该函数，则调用 `GetFunctionFromTokenAndTypeArgs` 将导致加载，这在许多上下文中是一个危险操作。 例如，在模块或类型加载过程中调用此方法可能会导致无限循环，因为运行时尝试循环加载某些功能。  
  
 通常，不建议使用 `GetFunctionFromTokenAndTypeArgs`。 如果探查器对特定函数的事件感兴趣，则它们应存储该函数的 `ModuleID` 和 `mdMethodDef`，并使用[ICorProfilerInfo2：： GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)来检查给定的 `FunctionID` 是否为所需函数的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
