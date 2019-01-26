---
title: ICorProfilerInfo::GetClassIDInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97465b5d39b3f6adbb6bccfc7b478ddad97066fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563725"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a>ICorProfilerInfo::GetClassIDInfo 方法
获取指定的类的父模块和元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
#### <a name="parameters"></a>参数  
 `classId`  
 [in]若要获取的信息的类的 ID。  
  
 `pModuleId`  
 [out]指向类的父模块 ID 的指针。  
  
 `pTypeDefToken`  
 [out]指向类的元数据标记的指针。  
  
## <a name="remarks"></a>备注  
 探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)以获取给定模块的元数据接口。 返回至 `pTypeDefToken` 所引用的位置的元数据标记可用于访问类的元数据。  
  
 若要获取泛型类型的详细信息，请使用[ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
