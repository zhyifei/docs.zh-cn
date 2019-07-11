---
title: ICeeGen::AddSectionReloc 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da3b83191ce1acdf40e27c5ee1d843a1fb4a54f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750673"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="f9daa-102">ICeeGen::AddSectionReloc 方法</span><span class="sxs-lookup"><span data-stu-id="f9daa-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="f9daa-103">将.reloc 指令添加到基本代码。</span><span class="sxs-lookup"><span data-stu-id="f9daa-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="f9daa-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="f9daa-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9daa-105">语法</span><span class="sxs-lookup"><span data-stu-id="f9daa-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9daa-106">参数</span><span class="sxs-lookup"><span data-stu-id="f9daa-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="f9daa-107">[in]要向其中添加.reloc 指令的内存中代码的部分。</span><span class="sxs-lookup"><span data-stu-id="f9daa-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="f9daa-108">[in]节的偏移量。</span><span class="sxs-lookup"><span data-stu-id="f9daa-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="f9daa-109">[in]向其部分`offset`引用。</span><span class="sxs-lookup"><span data-stu-id="f9daa-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="f9daa-110">[in]之一[CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md)值，它指示.reloc 指令，若要添加的类型。</span><span class="sxs-lookup"><span data-stu-id="f9daa-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9daa-111">要求</span><span class="sxs-lookup"><span data-stu-id="f9daa-111">Requirements</span></span>  
 <span data-ttu-id="f9daa-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9daa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9daa-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f9daa-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9daa-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f9daa-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9daa-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9daa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9daa-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9daa-116">See also</span></span>

- [<span data-ttu-id="f9daa-117">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="f9daa-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
