---
title: ICorDebugProcess::EnableLogMessages 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe237ca01d409636f184930d26ca970d58e90437
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472947"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="b67bd-102">ICorDebugProcess::EnableLogMessages 方法</span><span class="sxs-lookup"><span data-stu-id="b67bd-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="b67bd-103">启用和禁用到调试器的日志消息的传输。</span><span class="sxs-lookup"><span data-stu-id="b67bd-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b67bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="b67bd-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b67bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="b67bd-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="b67bd-106">[in]`true`即可传输日志消息;`false`禁用传输。</span><span class="sxs-lookup"><span data-stu-id="b67bd-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b67bd-107">备注</span><span class="sxs-lookup"><span data-stu-id="b67bd-107">Remarks</span></span>  
 <span data-ttu-id="b67bd-108">此方法无效后，才[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调发生。</span><span class="sxs-lookup"><span data-stu-id="b67bd-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b67bd-109">要求</span><span class="sxs-lookup"><span data-stu-id="b67bd-109">Requirements</span></span>  
 <span data-ttu-id="b67bd-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b67bd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b67bd-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b67bd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b67bd-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b67bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b67bd-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b67bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
