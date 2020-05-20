---
title: IApartmentCallback::DoCallback 方法
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
ms.openlocfilehash: 1a56c3ebe4b1c528f9c6555bdfbf1270a438410d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617108"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="3df30-102">IApartmentCallback::DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="3df30-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="3df30-103">在单元内执行指定的函数。</span><span class="sxs-lookup"><span data-stu-id="3df30-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3df30-104">语法</span><span class="sxs-lookup"><span data-stu-id="3df30-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3df30-105">参数</span><span class="sxs-lookup"><span data-stu-id="3df30-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="3df30-106">中指向要在单元中执行的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="3df30-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="3df30-107">中指向函数的自变量的指针。</span><span class="sxs-lookup"><span data-stu-id="3df30-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3df30-108">要求</span><span class="sxs-lookup"><span data-stu-id="3df30-108">Requirements</span></span>  
 <span data-ttu-id="3df30-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3df30-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3df30-110">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3df30-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3df30-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3df30-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3df30-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3df30-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df30-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3df30-113">See also</span></span>

- [<span data-ttu-id="3df30-114">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3df30-114">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
