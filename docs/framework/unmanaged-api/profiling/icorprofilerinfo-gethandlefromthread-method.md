---
title: "ICorProfilerInfo::GetHandleFromThread 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetHandleFromThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be925bbbcc86785feae28353dbc6563974aae2c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogethandlefromthread-method"></a>ICorProfilerInfo::GetHandleFromThread 方法
映射到 Win32 线程句柄的线程的 ID。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
#### <a name="parameters"></a>参数  
 `threadId`  
 [in]要映射的线程 ID。  
  
 `phThread`  
 [out]指向 Win32 线程句柄的指针。  
  
## <a name="remarks"></a>备注  
 探查器必须调用 Win32`DuplicateHandle`才能使用该句柄上的函数。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
