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
ms.openlocfilehash: 99eef11c294dbb17b30b2ef28e65999d4d60f817
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008309"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="e15ff-102">ICeeGen::GetMethodBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="e15ff-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="e15ff-103">获取指定的相对虚拟地址处的方法的适当大小的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e15ff-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="e15ff-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="e15ff-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e15ff-105">语法</span><span class="sxs-lookup"><span data-stu-id="e15ff-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e15ff-106">参数</span><span class="sxs-lookup"><span data-stu-id="e15ff-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="e15ff-107">中要为其返回缓冲区的方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="e15ff-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="e15ff-108">弄指向返回的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="e15ff-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e15ff-109">要求</span><span class="sxs-lookup"><span data-stu-id="e15ff-109">Requirements</span></span>  
 <span data-ttu-id="e15ff-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e15ff-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e15ff-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="e15ff-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e15ff-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e15ff-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e15ff-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e15ff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e15ff-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e15ff-114">See also</span></span>

- [<span data-ttu-id="e15ff-115">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="e15ff-115">ICeeGen Interface</span></span>](iceegen-interface.md)
