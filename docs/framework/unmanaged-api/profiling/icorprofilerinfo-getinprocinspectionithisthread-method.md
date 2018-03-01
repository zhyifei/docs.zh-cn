---
title: "ICorProfilerInfo::GetInprocInspectionIThisThread 方法"
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
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c36688af3ab8941a7004061add8598a480f3e202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a>ICorProfilerInfo::GetInprocInspectionIThisThread 方法
ICorDebugThread 接口获取可以查询的对象。 此方法是.NET Framework 2.0 版中过时。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a>参数  
 `ppicd`  
 [out](/cpp/atl/iunknown)为查询的对象`ICorDebugThread`接口。  
  
## <a name="remarks"></a>备注  
 公共语言运行时 (CLR) 调试服务支持在.NET Framework 1.0 版中的有限进程内调试。 探查器使用了调试 API 的检查部分启用进程内调试。 由于客户反馈，进程内调试已从.NET Framework 2.0 版中，在中删除和替换为一组是根据分析 API 的详细信息的功能。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 1.0  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
