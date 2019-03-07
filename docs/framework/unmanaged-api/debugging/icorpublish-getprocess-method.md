---
title: ICorPublish::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc13ec58e1830e6fb5aab5ae50dfc7a983ffc9f4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499675"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="72bf7-102">ICorPublish::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="72bf7-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="72bf7-103">获取[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)实例，它表示具有指定标识符的进程。</span><span class="sxs-lookup"><span data-stu-id="72bf7-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72bf7-104">语法</span><span class="sxs-lookup"><span data-stu-id="72bf7-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72bf7-105">参数</span><span class="sxs-lookup"><span data-stu-id="72bf7-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="72bf7-106">[in]进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="72bf7-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="72bf7-107">[out]指向的地址的指针`ICorPublishProcess`表示进程的实例。</span><span class="sxs-lookup"><span data-stu-id="72bf7-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72bf7-108">备注</span><span class="sxs-lookup"><span data-stu-id="72bf7-108">Remarks</span></span>  
 <span data-ttu-id="72bf7-109">`GetProcess` 如果进程不存在，或不是可调试由当前用户的托管的进程将失败。</span><span class="sxs-lookup"><span data-stu-id="72bf7-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72bf7-110">要求</span><span class="sxs-lookup"><span data-stu-id="72bf7-110">Requirements</span></span>  
 <span data-ttu-id="72bf7-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72bf7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72bf7-112">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="72bf7-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="72bf7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72bf7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72bf7-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72bf7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72bf7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="72bf7-115">See also</span></span>
- [<span data-ttu-id="72bf7-116">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="72bf7-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
