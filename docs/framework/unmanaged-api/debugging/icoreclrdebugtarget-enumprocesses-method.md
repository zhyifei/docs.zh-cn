---
title: "ICoreClrDebugTarget::EnumProcesses 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget.EnumProcesses
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8296b4b137032400ee172b6d3670bc1a53dbe60d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a>ICoreClrDebugTarget::EnumProcesses 方法
枚举远程计算机上运行的进程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pcProcs`  
 [out] `ppProcs` 中返回的进程数。 此值可为 0（零）。  
  
 `ppProcs`  
 [out]数组[CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)这些结构表示在远程计算机上运行的进程。  
  
## <a name="return-value"></a>返回值  
 S_OK  
 成功。  
  
 E_OUTOFMEMORY  
 无法为 `ppProcs` 分配足够的内存。  
  
 E_FAIL（或其他 E_ 返回代码）  
 其他故障。  
  
## <a name="remarks"></a>备注  
 若要释放由此方法分配的内存，调用[icoreclrdebugtarget:: Freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CoreClrRemoteDebuggingInterfaces.h  
  
 **库：** mscordbi_macx86.dll  
  
 **.NET framework 版本：** 3.5 SP1  
  
## <a name="see-also"></a>请参阅  
 [ICoreClrDebugTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
