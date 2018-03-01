---
title: "ICorProfilerInfo2::GetAppDomainStaticAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2fad6cccc3992f001780bf8bd1a4c879dc6aa754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>ICorProfilerInfo2::GetAppDomainStaticAddress 方法
获取指定的应用程序域范围内的指定的应用程序域的静态字段的地址。  
  
## <a name="syntax"></a>语法  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>参数  
 `classId`  
 [in]包含请求的应用程序域静态字段的类的类 ID。  
  
 `fieldToken`  
 [in]请求的应用程序域静态字段的元数据标记。  
  
 `appDomainId`  
 [in]为请求的静态字段的作用域的应用程序域的 ID。  
  
 `ppAddress`  
 [out]指向指定的应用程序域中的静态字段的地址的指针。  
  
## <a name="remarks"></a>备注  
 `GetAppDomainStaticAddress`方法可能会返回以下项之一：  
  
-   如果尚未分配为给定的静态字段指定的上下文中的地址 CORPROF_E_DATAINCOMPLETE HRESULT。  
  
-   可能会在垃圾回收堆中的对象的地址。 这些地址可能会变得无效垃圾回收后，以便垃圾回收后，探查器不应假定它们有效。  
  
 完成的类的类构造函数之前，`GetAppDomainStaticAddress`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，尽管可能已初始化的静态字段的一些和定位垃圾回收对象。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
