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
ms.openlocfilehash: 585287f63f57f55e877c94684820833b6d1add60
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616530"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="ca151-102">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="ca151-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="ca151-103">卸载托管模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="ca151-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="ca151-104">未实现此函数。</span><span class="sxs-lookup"><span data-stu-id="ca151-104">This function is not implemented.</span></span> <span data-ttu-id="ca151-105">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="ca151-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca151-106">语法</span><span class="sxs-lookup"><span data-stu-id="ca151-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca151-107">参数</span><span class="sxs-lookup"><span data-stu-id="ca151-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="ca151-108">中一个指针，指向要卸载的图像的起始位置。</span><span class="sxs-lookup"><span data-stu-id="ca151-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca151-109">要求</span><span class="sxs-lookup"><span data-stu-id="ca151-109">Requirements</span></span>  
 <span data-ttu-id="ca151-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca151-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca151-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ca151-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca151-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ca151-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca151-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca151-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca151-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca151-114">See also</span></span>

- [<span data-ttu-id="ca151-115">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="ca151-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
