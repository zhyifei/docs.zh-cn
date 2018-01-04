---
title: "IDebuggerThreadControl::ThreadIsBlockingForDebugger 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59a4c13e84414dcd10b217134334777a745431c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a>IDebuggerThreadControl::ThreadIsBlockingForDebugger 方法
通知正在发送此回调的线程即将主机到调试服务内的块。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a>备注  
 `ThreadIsBlockingForDebugger`始终将在运行时线程上调用方法。  
  
 `ThreadIsBlockingForDebugger`方法，该主机能够执行其他操作，而此线程受到阻止。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IDebuggerThreadControl 接口](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
