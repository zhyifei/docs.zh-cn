---
title: "ICorProfilerInfo2::GetRVAStaticAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetRVAStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type: apiref
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64553e8f611a8111aaaf9ababd1a7556f1192740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a>ICorProfilerInfo2::GetRVAStaticAddress 方法
获取指定的相对虚拟地址 (RVA) 的静态字段的地址。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>参数  
 `classId`  
 [in]包含请求的 RVA 静态字段的类 ID。  
  
 `fieldToken`  
 [in]请求的 RVA 静态字段的元数据标记。  
  
 `ppAddress`  
 [out]指向 RVA 静态字段的地址的指针。  
  
## <a name="remarks"></a>备注  
 `GetRVAStaticAddress`方法可能会返回以下项之一：  
  
-   如果尚未分配为给定的静态字段指定的上下文中的地址 CORPROF_E_DATAINCOMPLETE HRESULT。  
  
-   可能会在垃圾回收堆中的对象的地址。 这些地址可能会变得无效垃圾回收后，以便垃圾回收后，探查器不应假定它们有效。  
  
 完成的类的类构造函数之前，`GetRVAStaticAddress`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，但某些的静态字段可能已初始化，并可能会定位垃圾回收对象。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
