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
ms.openlocfilehash: 4932e1fd6294f4a01264e982835dd0707324082a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178235"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="bbca2-102">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="bbca2-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="bbca2-103">卸载托管模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="bbca2-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="bbca2-104">未实现此函数。</span><span class="sxs-lookup"><span data-stu-id="bbca2-104">This function is not implemented.</span></span> <span data-ttu-id="bbca2-105">如果调用，它将返回E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="bbca2-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbca2-106">语法</span><span class="sxs-lookup"><span data-stu-id="bbca2-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbca2-107">parameters</span><span class="sxs-lookup"><span data-stu-id="bbca2-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="bbca2-108">[在]指向要卸载的图像的起始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="bbca2-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbca2-109">要求</span><span class="sxs-lookup"><span data-stu-id="bbca2-109">Requirements</span></span>  
 <span data-ttu-id="bbca2-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbca2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbca2-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="bbca2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bbca2-112">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="bbca2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bbca2-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbca2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbca2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbca2-114">See also</span></span>

- [<span data-ttu-id="bbca2-115">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="bbca2-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
