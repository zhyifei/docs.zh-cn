---
title: ICorProfilerInfo::GetILFunctionBody 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 484fb5b8398e3ebd61d1c300afec1536ee1dc0c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780598"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody 方法
获取一个指针指向方法的主体在 Microsoft 中间语言 (MSIL) 代码中，从其标头处开始。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a>参数  
 `moduleId`  
 [in]该函数所在的模块的 ID。  
  
 `methodId`  
 [in]方法的元数据标记。  
  
 `ppMethodHeader`  
 [out]指向方法的标头的指针。  
  
 `pcbMethodSize`  
 [out]一个整数，指定方法的大小。  
  
## <a name="remarks"></a>备注  
 一种方法是按其所在的模块限定范围。 因为`GetILFunctionBody`方法旨在为访问工具提供对 MSIL 代码，然后加载公共语言运行时 (CLR)，它使用的元数据标记的方法来查找所需的实例。  
  
 `GetILFunctionBody` 如果可以返回 CORPROF_E_FUNCTION_NOT_IL HRESULT`methodId`指向一种方法，没有任何 MSIL 代码 （如一个抽象方法或平台调用 (PInvoke) 方法）。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
