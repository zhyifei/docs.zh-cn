---
title: "ICorProfilerFunctionControl::SetILFunctionBody 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56d31b93385a087949121a76587ef6009cd9d51e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>ICorProfilerFunctionControl::SetILFunctionBody 方法
替换方法的公共中间语言 (CIL) 主体。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a>参数  
 `cbNewILMethodHeader`  
 [in] 新 CIL 的总体大小，包括标头和主体之后的任何结构。  
  
 `pbNewILMethodHeader`  
 [in] 一个指向新 CIL 的标头的指针。  
  
## <a name="return-value"></a>返回值  
 此方法会返回以下特定的 HRESULT。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|替换成功。|  
  
## <a name="remarks"></a>备注  
 与不同[icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法，`SetILFunctionBody`方法管理新 CIL 的主体所需的内存。 这意味着探查器提供的 CIL 主体不必使用分配[IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)接口或在特定范围内。 它可在任何堆上进行分配。 探查器可以释放用于其 CIL 主体之后的内存`SetILFunctionBody`返回。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerFunctionControl 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
