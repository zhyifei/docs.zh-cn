---
title: ICorProfilerInfo::GetClassFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 6999821412b3cdd614cb30858a0616c9f27a6baa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448108"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>ICorProfilerInfo::GetClassFromToken 方法
给定元数据标记，获取类的 ID。 此方法在 .NET Framework 版本2.0 中已过时。 改[为使用 ICorProfilerInfo2：： GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>参数  
 `moduleID`  
 中包含类的模块的 ID。  
  
 `typeDef`  
 中引用类的 `mdTypeDef` 元数据标记。  
  
 `cTypeArgs`  
 弄指向类 ID 的指针。  
  
## <a name="remarks"></a>备注  
 此方法已过时;相反，请对所有类型使用 `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** 1.0、1。1  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
