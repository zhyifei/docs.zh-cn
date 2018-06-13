---
title: ICorDebugProcess::GetHandle 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60bd7567f541a0bbaa3591d2f2905d13064dec3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423437"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="6b621-102">ICorDebugProcess::GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="6b621-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="6b621-103">获取进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="6b621-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b621-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b621-104">Syntax</span></span>  
  
```  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b621-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b621-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="6b621-106">[out]指向的指针`HPROCESS`，它是进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="6b621-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b621-107">备注</span><span class="sxs-lookup"><span data-stu-id="6b621-107">Remarks</span></span>  
 <span data-ttu-id="6b621-108">检索到的句柄归调试接口。</span><span class="sxs-lookup"><span data-stu-id="6b621-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="6b621-109">调试器应重复使用它之前的句柄。</span><span class="sxs-lookup"><span data-stu-id="6b621-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b621-110">要求</span><span class="sxs-lookup"><span data-stu-id="6b621-110">Requirements</span></span>  
 <span data-ttu-id="6b621-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b621-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b621-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b621-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b621-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b621-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b621-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b621-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
