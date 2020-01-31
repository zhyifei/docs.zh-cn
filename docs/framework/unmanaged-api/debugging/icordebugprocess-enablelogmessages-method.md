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
ms.openlocfilehash: 6b1ccffa4f24122e643a64270f44945afdbc8fff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792653"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="978a6-102">ICorDebugProcess::EnableLogMessages 方法</span><span class="sxs-lookup"><span data-stu-id="978a6-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="978a6-103">启用和禁用向调试器传输日志消息。</span><span class="sxs-lookup"><span data-stu-id="978a6-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="978a6-104">语法</span><span class="sxs-lookup"><span data-stu-id="978a6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="978a6-105">参数</span><span class="sxs-lookup"><span data-stu-id="978a6-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="978a6-106">[in] `true` 允许传输日志消息;`false` 禁用传输。</span><span class="sxs-lookup"><span data-stu-id="978a6-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="978a6-107">备注</span><span class="sxs-lookup"><span data-stu-id="978a6-107">Remarks</span></span>  
 <span data-ttu-id="978a6-108">此方法仅在[ICorDebugManagedCallback：： CreateProcess](icordebugmanagedcallback-createprocess-method.md)回调发生之后有效。</span><span class="sxs-lookup"><span data-stu-id="978a6-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="978a6-109">需求</span><span class="sxs-lookup"><span data-stu-id="978a6-109">Requirements</span></span>  
 <span data-ttu-id="978a6-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="978a6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="978a6-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="978a6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="978a6-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="978a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="978a6-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="978a6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
