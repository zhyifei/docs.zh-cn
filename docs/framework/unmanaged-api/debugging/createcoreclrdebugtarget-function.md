---
title: "CreateCoreClrDebugTarget 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateCorClrDebugTarget
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1f52bddb5d5f11d36fcf8b833dd6fe65f9c0a4c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget 函数
创建一个与运行在远程计算机上，并返回的调试器代理连接[ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)可以用于查询正在运行的进程和远程计算机上加载的运行时对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwAddress`  
 [in] 远程目标计算机的 IPv4 地址。  
  
 `ppTarget`  
 [out]指针到指向[ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)将创建的对象。  
  
## <a name="return-value"></a>返回值  
 S_OK  
 已成功确定该进程中的 CLR 的数目，并已正确填写相应的句柄数组和路径数组。  
  
 E_OUTOFMEMORY  
 无法为 `ppTarget` 分配足够的内存。  
  
 E_FAIL（或其他 E_ 返回代码）  
 其他故障。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CoreClrRemoteDebuggingInterfaces.h  
  
 **库：** mscordbi_macx86.dll  
  
 **.NET framework 版本：** 3.5 SP1
