---
title: "ICorProfilerCallback::ModuleLoadFinished 方法"
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
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 360c14ccdd67cb7609ffe2f9c49914fdda163389
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a>ICorProfilerCallback::ModuleLoadFinished 方法
通知探查器加载已完成某个模块。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a>参数  
 `moduleId`  
 [in]已完成加载模块的 ID。  
  
 `hrStatus`  
 [in]指示是否已成功加载了该模块的 HRESULT。  
  
## <a name="remarks"></a>备注  
 值`moduleId`无效的信息请求之前，不能`ModuleLoadFinished`调用方法。  
  
 加载模块的某些部分可能会继续之后`ModuleLoadFinished`回调。 失败的 HRESULT 在`hrStatus`指示失败。 但是，HRESULT 为成功，在`hrStatus`仅指示已成功加载模块的第一部分。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ModuleLoadStarted 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
