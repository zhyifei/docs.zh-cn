---
title: ICeeGen::GetMethodBuffer 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8ccaa1b03ae1afc87eb7b0a66dd517bba8fcf8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497465"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="a61b7-102">ICeeGen::GetMethodBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="a61b7-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="a61b7-103">获取在指定的相对虚拟地址的方法的适当大小的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="a61b7-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="a61b7-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="a61b7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a61b7-105">语法</span><span class="sxs-lookup"><span data-stu-id="a61b7-105">Syntax</span></span>  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a61b7-106">参数</span><span class="sxs-lookup"><span data-stu-id="a61b7-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="a61b7-107">[in]要为其返回缓冲区的方法相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="a61b7-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="a61b7-108">[out]指向返回的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="a61b7-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a61b7-109">要求</span><span class="sxs-lookup"><span data-stu-id="a61b7-109">Requirements</span></span>  
 <span data-ttu-id="a61b7-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a61b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a61b7-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a61b7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a61b7-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a61b7-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a61b7-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a61b7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a61b7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a61b7-114">See also</span></span>
- [<span data-ttu-id="a61b7-115">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="a61b7-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
