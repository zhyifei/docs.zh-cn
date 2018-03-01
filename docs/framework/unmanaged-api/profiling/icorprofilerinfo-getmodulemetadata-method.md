---
title: "ICorProfilerInfo::GetModuleMetaData 方法"
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
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6ad52460bcd6eb320e970cd0ce2078f2e93df353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>ICorProfilerInfo::GetModuleMetaData 方法
获取映射到指定的模块的元数据接口实例。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a>参数  
 `moduleId`  
 [in]接口实例将映射到模块的 ID。  
  
 `dwOpenFlags`  
 [in]值为[CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)指定打开清单文件的模式的枚举。 仅`ofRead`，`ofWrite`和`ofNoTransform`位均有效。  
  
 `riid`  
 [in]引用的元数据接口将检索其实例的 ID (GUID)。 请参阅[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)的接口的列表。  
  
 `ppOut`  
 [out]指向元数据接口实例的地址的指针。  
  
## <a name="remarks"></a>备注  
 你可能会要求针对元数据要打开在读/写模式下，但这将导致该程序的执行速度变慢的元数据，因为对更改它们从编译器的不能优化元数据。  
  
 一些模块 （如资源模块） 具有任何元数据。 在这些情况下，`GetModuleMetaData`将返回的 HRESULT 值为 S_FALSE 和中的 null *`ppOut`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
