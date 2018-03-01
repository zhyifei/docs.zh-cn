---
title: "ICorProfilerCallback::AppDomainCreationStarted 方法"
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
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe9089438f64bff19439af76c3f5eaf18fc5d6d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a>ICorProfilerCallback::AppDomainCreationStarted 方法
通知探查器创建应用程序域。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a>参数  
 `appDomainId`  
 [in]标识正在创建的域。  
  
## <a name="remarks"></a>备注  
 ID 不是有效的任何信息请求到[icorprofilercallback:: Appdomaincreationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)调用方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
