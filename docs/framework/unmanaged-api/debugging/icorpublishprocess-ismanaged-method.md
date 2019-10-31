---
title: ICorPublishProcess::IsManaged 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: ad3a357a98cb5ed28a34e4076b5e145903ceaf91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103501"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="4f355-102">ICorPublishProcess::IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="4f355-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="4f355-103">获取一个值，该值指示此[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)引用的进程是否已知具有托管代码。</span><span class="sxs-lookup"><span data-stu-id="4f355-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f355-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f355-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f355-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f355-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="4f355-106">弄一个指向布尔值的指针，该布尔值指示进程是否具有托管代码。</span><span class="sxs-lookup"><span data-stu-id="4f355-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="4f355-107">如果进程具有托管代码，则值为 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="4f355-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f355-108">备注</span><span class="sxs-lookup"><span data-stu-id="4f355-108">Remarks</span></span>  
 <span data-ttu-id="4f355-109">由于 `ICorPublishProcess` 的当前版本只允许访问具有托管代码的进程，`IsManaged` 总是返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="4f355-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f355-110">要求</span><span class="sxs-lookup"><span data-stu-id="4f355-110">Requirements</span></span>  
 <span data-ttu-id="4f355-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f355-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f355-112">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="4f355-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4f355-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f355-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f355-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f355-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f355-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f355-115">See also</span></span>

- [<span data-ttu-id="4f355-116">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="4f355-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
