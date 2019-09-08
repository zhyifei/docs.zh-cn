---
title: CreateAssemblyCache 函数
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c855d6f85c3cbfa6d81a1fbce3ef5b83abb3f583
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795406"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="ae4ab-102">CreateAssemblyCache 函数</span><span class="sxs-lookup"><span data-stu-id="ae4ab-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="ae4ab-103">获取一个指针，该指针指向表示全局程序集缓存的新[IAssemblyCache](iassemblycache-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="ae4ab-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae4ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae4ab-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae4ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae4ab-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="ae4ab-106">弄返回`IAssemblyCache`的指针。</span><span class="sxs-lookup"><span data-stu-id="ae4ab-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="ae4ab-107">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="ae4ab-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ae4ab-108">`dwReserved`必须为0（零）。</span><span class="sxs-lookup"><span data-stu-id="ae4ab-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae4ab-109">要求</span><span class="sxs-lookup"><span data-stu-id="ae4ab-109">Requirements</span></span>  
 <span data-ttu-id="ae4ab-110">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae4ab-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae4ab-111">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="ae4ab-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ae4ab-112">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ae4ab-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae4ab-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae4ab-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4ab-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae4ab-114">See also</span></span>

- [<span data-ttu-id="ae4ab-115">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="ae4ab-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="ae4ab-116">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="ae4ab-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="ae4ab-117">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="ae4ab-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
