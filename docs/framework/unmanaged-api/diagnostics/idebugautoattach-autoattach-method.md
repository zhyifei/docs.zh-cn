---
title: "IDebugAutoAttach::AutoAttach 方法"
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
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b875fec2fdb6ecaeaccf8e58030b2fccbb8653b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugautoattachautoattach-method"></a>IDebugAutoAttach::AutoAttach 方法
执行服务器调用调试器自动附加。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `guidPort`  
 [in]始终设置为`GUID_NULL`。  
  
 `dwPid`  
 [in]进程 ID，通常使用检索`GetCurrentProcessId`函数。  
  
 `dwProgramType`  
 [in]程序类型： `AUTOATTACH_PROGRAM_WIN32`， `AUTOATTACH_PROGRAM_COMPLUS`，或`AUTOATTACH_PROGRAM_UNKNOWN`。  
  
 `dwProgramId`  
 [in]程序 id。  
  
 `pszSessionId`  
 [in]通过 debug 谓词传递的字符串。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则为 S_OK。  
  
## <a name="requirements"></a>惠?  
 **标头：** DbgAutoAttach.h  
  
## <a name="see-also"></a>请参阅  
 [IDebugAutoAttach 接口](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
