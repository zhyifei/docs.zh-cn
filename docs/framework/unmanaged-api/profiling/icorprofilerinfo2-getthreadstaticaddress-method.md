---
title: "ICorProfilerInfo2::GetThreadStaticAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetThreadStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type: apiref
caps.latest.revision: "24"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25deb36e935649c9a10d87872407c9a0d490239e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a>ICorProfilerInfo2::GetThreadStaticAddress 方法
获取指定线程的范围内的指定线程静态字段的地址。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
#### <a name="parameters"></a>参数  
 `classId`  
 [in]包含请求的线程静态字段的类 ID。  
  
 `fieldToken`  
 [in]请求的线程静态字段的元数据标记。  
  
 `threadId`  
 [in]是请求的静态字段的作用域的线程 ID。  
  
 `ppAddress`  
 [out]指向位于指定线程静态字段的地址的指针。  
  
## <a name="remarks"></a>备注  
 `GetThreadStaticAddress`方法可能会返回以下项之一：  
  
-   如果尚未分配为给定的静态字段指定的上下文中的地址 CORPROF_E_DATAINCOMPLETE HRESULT。  
  
-   可能会在垃圾回收堆中的对象的地址。 这些地址可能会变得无效垃圾回收之后，因此在之后垃圾集合探查器不应假定它们是否有效。  
  
 完成的类的类构造函数之前，`GetThreadStaticAddress`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，尽管可能已初始化的静态字段的一些和定位垃圾回收对象。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
