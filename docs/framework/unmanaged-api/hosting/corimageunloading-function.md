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
ms.openlocfilehash: 30e3a88140c8a438001e8428df4c5ee879c83376
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136913"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="a3bbf-102">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="a3bbf-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="a3bbf-103">卸载托管模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="a3bbf-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="a3bbf-104">未实现此函数。</span><span class="sxs-lookup"><span data-stu-id="a3bbf-104">This function is not implemented.</span></span> <span data-ttu-id="a3bbf-105">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="a3bbf-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3bbf-106">语法</span><span class="sxs-lookup"><span data-stu-id="a3bbf-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3bbf-107">参数</span><span class="sxs-lookup"><span data-stu-id="a3bbf-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="a3bbf-108">中一个指针，指向要卸载的图像的起始位置。</span><span class="sxs-lookup"><span data-stu-id="a3bbf-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3bbf-109">要求</span><span class="sxs-lookup"><span data-stu-id="a3bbf-109">Requirements</span></span>  
 <span data-ttu-id="a3bbf-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3bbf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3bbf-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="a3bbf-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3bbf-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a3bbf-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3bbf-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3bbf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3bbf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3bbf-114">See also</span></span>

- [<span data-ttu-id="a3bbf-115">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="a3bbf-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
