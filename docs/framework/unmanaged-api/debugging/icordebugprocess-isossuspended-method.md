---
title: "ICorDebugProcess::IsOSSuspended 方法"
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
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended 方法
获取一个值，该值指示指定的线程是否已挂起由于调试器停止此过程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a>参数  
 `threadID`  
 [in]问题的线程的 ID。  
  
 `pbSuspended`  
 [out]一个布尔值，是一个指向`true`如果指定的线程已挂起; 否则为 *`pbSuspended`是`false`。  
  
## <a name="remarks"></a>备注  
 当指定的线程已被暂停由于调试器停止此过程中时，指定的线程的 Win32 挂起计数就会递增 1。 调试器用户界面 (UI) 可能要将此信息打包在帐户，如果该命令显示操作系统 (OS) 挂起的用户的线程计数。  
  
 `IsOSSuspended`方法有意义仅在非托管调试上下文中。 托管在调试期间，线程是以协作方式挂起而不是操作系统挂起。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
