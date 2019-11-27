---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
ms.openlocfilehash: 5b6c0159b432d2a70f583357bbcf714b27399633
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447173"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 方法
使用指定的元数据标记和任何类型参数的 `ClassID` 值获取类型的 `ClassID`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>参数  
 `moduleID`  
 中类型所在的模块的 ID。  
  
 `typeDef`  
 中引用类型的 `mdTypeDef` 元数据标记。  
  
 `cTypeArgs`  
 中给定类型的类型参数的数目。 对于非泛型类型，此值必须为零。  
  
 `typeArgs`  
 中`ClassID` 值的数组，其中每个值都是类型的参数。 如果 `cTypeArgs` 设置为零，则 `typeArgs` 的值可以为 NULL。  
  
 `pClassID`  
 弄指向指定类型的 `ClassID` 的指针。  
  
## <a name="remarks"></a>备注  
 使用 `mdTypeRef` 而不是 `mdTypeDef` 元数据令牌调用 `GetClassFromTokenAndTypeArgs` 方法可能会产生不可预知的结果;调用方应在传递时将 `mdTypeRef` 解析为 `mdTypeDef`。  
  
 如果尚未加载该类型，则调用 `GetClassFromTokenAndTypeArgs` 将触发加载，这在许多上下文中是一个危险操作。 例如，在加载模块或其他类型期间调用此方法可能会导致无限循环，因为运行时尝试循环加载某些功能。  
  
 通常，不建议使用 `GetClassFromTokenAndTypeArgs`。 如果探查器对特定类型的事件感兴趣，则它们应存储该类型的 `ModuleID` 和 `mdTypeDef`，并使用[ICorProfilerInfo2：： GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)来检查给定的 `ClassID` 是否为所需的类型。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
