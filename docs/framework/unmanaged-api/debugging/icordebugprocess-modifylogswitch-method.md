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
ms.openlocfilehash: 20ceed164631169b3a47809381b2cc4e630ae718
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418612"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="b49f2-102">ICorDebugProcess::ModifyLogSwitch 方法</span><span class="sxs-lookup"><span data-stu-id="b49f2-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="b49f2-103">设置指定的日志交换机的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="b49f2-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b49f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="b49f2-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b49f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="b49f2-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="b49f2-106">[in]指向一个字符串，指定日志交换机的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="b49f2-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="b49f2-107">[in]要为指定的日志交换机设置的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="b49f2-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b49f2-108">备注</span><span class="sxs-lookup"><span data-stu-id="b49f2-108">Remarks</span></span>  
 <span data-ttu-id="b49f2-109">此方法无效后，才[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调发生。</span><span class="sxs-lookup"><span data-stu-id="b49f2-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b49f2-110">要求</span><span class="sxs-lookup"><span data-stu-id="b49f2-110">Requirements</span></span>  
 <span data-ttu-id="b49f2-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b49f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b49f2-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b49f2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b49f2-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b49f2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b49f2-114">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b49f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
