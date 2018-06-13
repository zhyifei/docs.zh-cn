---
title: ICorProfilerInfo2::GetContextStaticAddress 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d787e3eae59218c46a95c327a0f93502c3833d9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456230"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>ICorProfilerInfo2::GetContextStaticAddress 方法
获取为指定的上下文范围内的指定上下文的静态字段的地址。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>参数  
 `classId`  
 [in]包含请求的上下文静态字段的类 ID。  
  
 `fieldToken`  
 [in]请求的上下文静态字段的元数据标记。  
  
 `contextId`  
 [in]与请求的上下文静态字段的作用域的上下文 ID。  
  
 `ppAddress`  
 [out]指向在指定的上下文内的静态字段的地址的指针。  
  
## <a name="remarks"></a>备注  
 `GetContextStaticAddress`方法可能会返回以下项之一：  
  
-   如果尚未分配为给定的静态字段指定的上下文中的地址 CORPROF_E_DATAINCOMPLETE HRESULT。  
  
-   可能会在垃圾回收堆中的对象的地址。 这些地址可能会变得无效垃圾回收后，以便垃圾回收后，探查器不应假定它们有效。  
  
 完成的类的类构造函数之前，`GetContextStaticAddress`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，尽管可能已初始化的静态字段的一些和定位垃圾回收对象。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
