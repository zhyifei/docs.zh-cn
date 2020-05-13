---
title: ICorDebugProcess::ModifyLogSwitch 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: c9375854b45432eafb6cc706a1a62f5424e0fee8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210483"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="debf9-102">ICorDebugProcess::ModifyLogSwitch 方法</span><span class="sxs-lookup"><span data-stu-id="debf9-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="debf9-103">设置指定的日志开关的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="debf9-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="debf9-104">语法</span><span class="sxs-lookup"><span data-stu-id="debf9-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="debf9-105">参数</span><span class="sxs-lookup"><span data-stu-id="debf9-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="debf9-106">中指向字符串的指针，该字符串指定日志开关的名称。</span><span class="sxs-lookup"><span data-stu-id="debf9-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="debf9-107">中要为指定的日志开关设置的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="debf9-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="debf9-108">备注</span><span class="sxs-lookup"><span data-stu-id="debf9-108">Remarks</span></span>  
 <span data-ttu-id="debf9-109">此方法仅在[ICorDebugManagedCallback：： CreateProcess](icordebugmanagedcallback-createprocess-method.md)回调发生之后有效。</span><span class="sxs-lookup"><span data-stu-id="debf9-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="debf9-110">要求</span><span class="sxs-lookup"><span data-stu-id="debf9-110">Requirements</span></span>  
 <span data-ttu-id="debf9-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="debf9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="debf9-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="debf9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="debf9-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="debf9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="debf9-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="debf9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
