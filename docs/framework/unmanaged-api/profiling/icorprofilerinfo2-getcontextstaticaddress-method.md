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
ms.openlocfilehash: d5d7da343148d5f1c2aa9b2b639b094f8269199b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433200"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>ICorProfilerInfo2::GetContextStaticAddress 方法
获取指定上下文的范围内的指定上下文静态字段的地址。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>参数  
 `classId`  
 中包含请求的上下文静态字段的类的 ID。  
  
 `fieldToken`  
 中请求的上下文静态字段的元数据标记。  
  
 `contextId`  
 中作为所请求的上下文静态字段的作用域的上下文的 ID。  
  
 `ppAddress`  
 弄指向指定上下文内的静态字段的地址的指针。  
  
## <a name="remarks"></a>备注  
 `GetContextStaticAddress` 方法可能会返回以下内容之一：  
  
- 如果未在指定的上下文中为给定的静态字段分配地址，则 CORPROF_E_DATAINCOMPLETE HRESULT。  
  
- 可能位于垃圾回收堆中的对象的地址。 这些地址可能会在垃圾回收后失效，因此，在垃圾回收后，探查器不应假定它们是有效的。  
  
 在类的类构造函数完成之前，尽管某些静态字段可能已经初始化并为垃圾回收对象提供了根，`GetContextStaticAddress` 仍将返回其所有静态字段的 CORPROF_E_DATAINCOMPLETE。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
