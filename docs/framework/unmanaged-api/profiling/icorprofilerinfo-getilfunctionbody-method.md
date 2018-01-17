---
title: "ICorProfilerInfo::GetILFunctionBody 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 035c2a1926d80b4aaea57523b4ecdd3da6873efe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody 方法
获取一个指针指向方法的正文在 Microsoft 中间语言 (MSIL) 代码中，开始其标头。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a>参数  
 `moduleId`  
 [in]函数所在模块的 ID。  
  
 `methodId`  
 [in]方法的元数据标记。  
  
 `ppMethodHeader`  
 [out]指向方法的标头的指针。  
  
 `pcbMethodSize`  
 [out]一个整数，指定方法的大小。  
  
## <a name="remarks"></a>备注  
 一种方法的作用范围由其所在的模块。 因为`GetILFunctionBody`方法旨在让 MSIL 代码的工具访问，公共语言运行时 (CLR) 加载之前，它使用该方法的元数据标记查找所需的实例。  
  
 `GetILFunctionBody`如果可以返回 CORPROF_E_FUNCTION_NOT_IL HRESULT`methodId`指向一种方法，无任何 MSIL 代码 （例如，一个抽象方法或平台 invoke (PInvoke) 方法)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
