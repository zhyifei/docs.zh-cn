---
title: ICeeGen::AllocateMethodBuffer 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7be1bd2934fbb2e09a39c3042fa9ae314e89d629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083759"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="f9643-102">ICeeGen::AllocateMethodBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="f9643-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="f9643-103">创建一个方法，为指定的大小的缓冲区并获取该方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="f9643-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="f9643-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="f9643-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9643-105">语法</span><span class="sxs-lookup"><span data-stu-id="f9643-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9643-106">参数</span><span class="sxs-lookup"><span data-stu-id="f9643-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="f9643-107">[in]要创建的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="f9643-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="f9643-108">[out]返回的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f9643-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="f9643-109">[out]相对虚拟地址的方法。</span><span class="sxs-lookup"><span data-stu-id="f9643-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9643-110">要求</span><span class="sxs-lookup"><span data-stu-id="f9643-110">Requirements</span></span>  
 <span data-ttu-id="f9643-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9643-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9643-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f9643-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9643-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f9643-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9643-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9643-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9643-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9643-115">See also</span></span>

- [<span data-ttu-id="f9643-116">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="f9643-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
