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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b1c85499e5269027da2c2a01ab67aab2c5da626
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775539"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="18c54-102">ICorDebugProcess::ModifyLogSwitch 方法</span><span class="sxs-lookup"><span data-stu-id="18c54-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="18c54-103">设置指定的日志开关的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="18c54-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c54-104">语法</span><span class="sxs-lookup"><span data-stu-id="18c54-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18c54-105">参数</span><span class="sxs-lookup"><span data-stu-id="18c54-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="18c54-106">[in]指向一个字符串，指定日志交换机的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="18c54-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="18c54-107">[in]要为指定的日志开关设置的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="18c54-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18c54-108">备注</span><span class="sxs-lookup"><span data-stu-id="18c54-108">Remarks</span></span>  
 <span data-ttu-id="18c54-109">此方法无效后，才[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调发生。</span><span class="sxs-lookup"><span data-stu-id="18c54-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18c54-110">要求</span><span class="sxs-lookup"><span data-stu-id="18c54-110">Requirements</span></span>  
 <span data-ttu-id="18c54-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18c54-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18c54-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18c54-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18c54-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18c54-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18c54-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18c54-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
