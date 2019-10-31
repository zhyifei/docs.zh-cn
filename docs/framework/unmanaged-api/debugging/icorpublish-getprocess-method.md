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
ms.openlocfilehash: a9d28243e9907fcc6320b2e09a49312bf35a70b4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121776"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="19c31-102">ICorPublish::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="19c31-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="19c31-103">获取一个表示具有指定标识符的进程的[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="19c31-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c31-104">语法</span><span class="sxs-lookup"><span data-stu-id="19c31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19c31-105">参数</span><span class="sxs-lookup"><span data-stu-id="19c31-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="19c31-106">中进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="19c31-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="19c31-107">弄一个指针，指向表示进程的 `ICorPublishProcess` 实例的地址。</span><span class="sxs-lookup"><span data-stu-id="19c31-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19c31-108">备注</span><span class="sxs-lookup"><span data-stu-id="19c31-108">Remarks</span></span>  
 <span data-ttu-id="19c31-109">如果进程不存在，或者当前用户无法调试托管进程，则 `GetProcess` 会失败。</span><span class="sxs-lookup"><span data-stu-id="19c31-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c31-110">要求</span><span class="sxs-lookup"><span data-stu-id="19c31-110">Requirements</span></span>  
 <span data-ttu-id="19c31-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19c31-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c31-112">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="19c31-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="19c31-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19c31-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19c31-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c31-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c31-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="19c31-115">See also</span></span>

- [<span data-ttu-id="19c31-116">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="19c31-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
