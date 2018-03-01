---
title: "ICeeGen::AllocateMethodBuffer 方法"
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
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b92d42878e9f3a8778208d8acf89de7618fc7c54
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="bda58-102">ICeeGen::AllocateMethodBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="bda58-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="bda58-103">创建方法，指定大小的缓冲区并获取该方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="bda58-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="bda58-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="bda58-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda58-105">语法</span><span class="sxs-lookup"><span data-stu-id="bda58-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bda58-106">参数</span><span class="sxs-lookup"><span data-stu-id="bda58-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="bda58-107">[in]要创建的缓冲区长度。</span><span class="sxs-lookup"><span data-stu-id="bda58-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="bda58-108">[out]返回的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="bda58-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="bda58-109">[out]相对虚拟地址的方法。</span><span class="sxs-lookup"><span data-stu-id="bda58-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda58-110">惠?</span><span class="sxs-lookup"><span data-stu-id="bda58-110">Requirements</span></span>  
 <span data-ttu-id="bda58-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bda58-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda58-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bda58-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bda58-113">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bda58-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bda58-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda58-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda58-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bda58-115">See Also</span></span>  
 [<span data-ttu-id="bda58-116">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="bda58-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
