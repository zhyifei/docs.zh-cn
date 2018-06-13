---
title: ICeeGen::GetSectionBlock 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5da2936a46dcf3d8f69acc3367db64712165b0cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444041"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="7ba2d-102">ICeeGen::GetSectionBlock 方法</span><span class="sxs-lookup"><span data-stu-id="7ba2d-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="7ba2d-103">获取部分块的基本代码。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="7ba2d-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ba2d-105">语法</span><span class="sxs-lookup"><span data-stu-id="7ba2d-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ba2d-106">参数</span><span class="sxs-lookup"><span data-stu-id="7ba2d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7ba2d-107">[in]要从中检索的基本代码块部分。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="7ba2d-108">[in]要检索的块的长度。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="7ba2d-109">[in]相对于开始部分中，用来对齐块的第一个字节的字节。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="7ba2d-110">这是块的部分中的位置。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="7ba2d-111">[out]指向接收检索到的块的地址的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ba2d-112">备注</span><span class="sxs-lookup"><span data-stu-id="7ba2d-112">Remarks</span></span>  
 <span data-ttu-id="7ba2d-113">调用`GetSectionBlock`仅当你有特殊的段中要求未由其他方法。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ba2d-114">要求</span><span class="sxs-lookup"><span data-stu-id="7ba2d-114">Requirements</span></span>  
 <span data-ttu-id="7ba2d-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ba2d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ba2d-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ba2d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ba2d-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7ba2d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ba2d-118">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ba2d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba2d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ba2d-119">See Also</span></span>  
 [<span data-ttu-id="7ba2d-120">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="7ba2d-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
