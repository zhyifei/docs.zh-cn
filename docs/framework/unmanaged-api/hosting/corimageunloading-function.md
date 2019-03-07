---
title: _CorImageUnloading 函数
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 72c851858ab2f294601d2e7f97b43e21ca815857
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474808"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="d76cc-102">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="d76cc-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="d76cc-103">卸载托管的模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="d76cc-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="d76cc-104">未实现此函数。</span><span class="sxs-lookup"><span data-stu-id="d76cc-104">This function is not implemented.</span></span> <span data-ttu-id="d76cc-105">如果调用，则返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="d76cc-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d76cc-106">语法</span><span class="sxs-lookup"><span data-stu-id="d76cc-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d76cc-107">参数</span><span class="sxs-lookup"><span data-stu-id="d76cc-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="d76cc-108">[in]指向要卸载的图像的起始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="d76cc-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d76cc-109">要求</span><span class="sxs-lookup"><span data-stu-id="d76cc-109">Requirements</span></span>  
 <span data-ttu-id="d76cc-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d76cc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d76cc-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d76cc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d76cc-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d76cc-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d76cc-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d76cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76cc-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d76cc-114">See also</span></span>
- [<span data-ttu-id="d76cc-115">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="d76cc-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
