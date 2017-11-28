---
title: "ICorDebugProcess::EnableLogMessages 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.EnableLogMessages
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7aecb0c72b58d1d46c3fd4d1137d6c303453706
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="df92a-102">ICorDebugProcess::EnableLogMessages 方法</span><span class="sxs-lookup"><span data-stu-id="df92a-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="df92a-103">启用和禁用的到调试器的日志消息传输。</span><span class="sxs-lookup"><span data-stu-id="df92a-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df92a-104">语法</span><span class="sxs-lookup"><span data-stu-id="df92a-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df92a-105">参数</span><span class="sxs-lookup"><span data-stu-id="df92a-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="df92a-106">[in]`true`启用的日志消息; 传输`false`禁用传输。</span><span class="sxs-lookup"><span data-stu-id="df92a-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df92a-107">备注</span><span class="sxs-lookup"><span data-stu-id="df92a-107">Remarks</span></span>  
 <span data-ttu-id="df92a-108">此方法无效后，才[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调时发生。</span><span class="sxs-lookup"><span data-stu-id="df92a-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df92a-109">要求</span><span class="sxs-lookup"><span data-stu-id="df92a-109">Requirements</span></span>  
 <span data-ttu-id="df92a-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df92a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df92a-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df92a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df92a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df92a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df92a-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df92a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
