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
ms.openlocfilehash: 0731053fb37c775d25052a5fd99a479a44ff5862
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434879"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="6e9a0-102">ICeeGen::GetSectionBlock 方法</span><span class="sxs-lookup"><span data-stu-id="6e9a0-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="6e9a0-103">获取代码库的节块。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="6e9a0-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e9a0-105">语法</span><span class="sxs-lookup"><span data-stu-id="6e9a0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="6e9a0-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e9a0-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="6e9a0-107">中要从中检索基本代码块的部分。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="6e9a0-108">中要检索的块的长度。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="6e9a0-109">中相对于部分开头的字节，用于对齐块的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="6e9a0-110">这是块在节中的位置。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="6e9a0-111">弄一个指针，指向接收检索到的块的地址的位置。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e9a0-112">备注</span><span class="sxs-lookup"><span data-stu-id="6e9a0-112">Remarks</span></span>  
 <span data-ttu-id="6e9a0-113">仅当你有其他方法未处理的特殊部分要求时，才调用 `GetSectionBlock`。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e9a0-114">要求</span><span class="sxs-lookup"><span data-stu-id="6e9a0-114">Requirements</span></span>  
 <span data-ttu-id="6e9a0-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e9a0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e9a0-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="6e9a0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e9a0-117">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6e9a0-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e9a0-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e9a0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9a0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e9a0-119">See also</span></span>

- [<span data-ttu-id="6e9a0-120">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="6e9a0-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
