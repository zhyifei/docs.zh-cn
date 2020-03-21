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
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176079"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="87cb5-102">ICeeGen::GetSectionBlock 方法</span><span class="sxs-lookup"><span data-stu-id="87cb5-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="87cb5-103">获取代码库的节块。</span><span class="sxs-lookup"><span data-stu-id="87cb5-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="87cb5-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="87cb5-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87cb5-105">语法</span><span class="sxs-lookup"><span data-stu-id="87cb5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="87cb5-106">parameters</span><span class="sxs-lookup"><span data-stu-id="87cb5-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="87cb5-107">[在]从中检索代码库块的部分。</span><span class="sxs-lookup"><span data-stu-id="87cb5-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="87cb5-108">[在]要检索的块的长度。</span><span class="sxs-lookup"><span data-stu-id="87cb5-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="87cb5-109">[在]相对于节的开头的字节，用于对齐块的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="87cb5-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="87cb5-110">这是块在节内的位置。</span><span class="sxs-lookup"><span data-stu-id="87cb5-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="87cb5-111">[出]指向接收检索的块地址的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="87cb5-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87cb5-112">备注</span><span class="sxs-lookup"><span data-stu-id="87cb5-112">Remarks</span></span>  
 <span data-ttu-id="87cb5-113">仅当`GetSectionBlock`您有特殊节要求时，其他方法未处理，才调用。</span><span class="sxs-lookup"><span data-stu-id="87cb5-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87cb5-114">要求</span><span class="sxs-lookup"><span data-stu-id="87cb5-114">Requirements</span></span>  
 <span data-ttu-id="87cb5-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87cb5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87cb5-116">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="87cb5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87cb5-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="87cb5-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87cb5-118">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87cb5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87cb5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87cb5-119">See also</span></span>

- [<span data-ttu-id="87cb5-120">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="87cb5-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
