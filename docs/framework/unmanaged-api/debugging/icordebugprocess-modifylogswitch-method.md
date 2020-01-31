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
ms.openlocfilehash: 27e13e298c1be61018a92e53a0ee82c786729c7d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792585"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="20144-102">ICorDebugProcess::ModifyLogSwitch 方法</span><span class="sxs-lookup"><span data-stu-id="20144-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="20144-103">设置指定的日志开关的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="20144-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20144-104">语法</span><span class="sxs-lookup"><span data-stu-id="20144-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20144-105">参数</span><span class="sxs-lookup"><span data-stu-id="20144-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="20144-106">中指向字符串的指针，该字符串指定日志开关的名称。</span><span class="sxs-lookup"><span data-stu-id="20144-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="20144-107">中要为指定的日志开关设置的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="20144-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20144-108">备注</span><span class="sxs-lookup"><span data-stu-id="20144-108">Remarks</span></span>  
 <span data-ttu-id="20144-109">此方法仅在[ICorDebugManagedCallback：： CreateProcess](icordebugmanagedcallback-createprocess-method.md)回调发生之后有效。</span><span class="sxs-lookup"><span data-stu-id="20144-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20144-110">需求</span><span class="sxs-lookup"><span data-stu-id="20144-110">Requirements</span></span>  
 <span data-ttu-id="20144-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20144-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20144-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20144-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20144-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20144-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20144-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20144-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
