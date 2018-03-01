---
title: "_CorImageUnloading 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f0c105e84d34e83320d6c7d159a94ba4148b302
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corimageunloading-function"></a><span data-ttu-id="9dbd7-102">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="9dbd7-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="9dbd7-103">卸载托管的模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="9dbd7-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="9dbd7-104">未实现此函数。</span><span class="sxs-lookup"><span data-stu-id="9dbd7-104">This function is not implemented.</span></span> <span data-ttu-id="9dbd7-105">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="9dbd7-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dbd7-106">语法</span><span class="sxs-lookup"><span data-stu-id="9dbd7-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9dbd7-107">参数</span><span class="sxs-lookup"><span data-stu-id="9dbd7-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="9dbd7-108">[in]指向要卸载的映像的起始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="9dbd7-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dbd7-109">惠?</span><span class="sxs-lookup"><span data-stu-id="9dbd7-109">Requirements</span></span>  
 <span data-ttu-id="9dbd7-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9dbd7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dbd7-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9dbd7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9dbd7-112">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9dbd7-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9dbd7-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dbd7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbd7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9dbd7-114">See Also</span></span>  
 [<span data-ttu-id="9dbd7-115">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="9dbd7-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
