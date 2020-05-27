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
ms.openlocfilehash: 2f66d34fcfdd8c61dcc92817ec1a928ac5b603fc
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008893"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="ceb25-102">ICeeGen::AddSectionReloc 方法</span><span class="sxs-lookup"><span data-stu-id="ceb25-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="ceb25-103">将 .reloc 指令添加到基本代码。</span><span class="sxs-lookup"><span data-stu-id="ceb25-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="ceb25-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="ceb25-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb25-105">语法</span><span class="sxs-lookup"><span data-stu-id="ceb25-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceb25-106">参数</span><span class="sxs-lookup"><span data-stu-id="ceb25-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="ceb25-107">中要将 .reloc 指令添加到的内存中代码部分。</span><span class="sxs-lookup"><span data-stu-id="ceb25-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="ceb25-108">中部分的偏移量。</span><span class="sxs-lookup"><span data-stu-id="ceb25-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="ceb25-109">中引用的部分 `offset` 。</span><span class="sxs-lookup"><span data-stu-id="ceb25-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="ceb25-110">中[CeeSectionRelocType](ceesectionreloctype-enumeration.md)值之一，指示要添加的 .reloc 指令的类型。</span><span class="sxs-lookup"><span data-stu-id="ceb25-110">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceb25-111">要求</span><span class="sxs-lookup"><span data-stu-id="ceb25-111">Requirements</span></span>  
 <span data-ttu-id="ceb25-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ceb25-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb25-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ceb25-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ceb25-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ceb25-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ceb25-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb25-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb25-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ceb25-116">See also</span></span>

- [<span data-ttu-id="ceb25-117">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="ceb25-117">ICeeGen Interface</span></span>](iceegen-interface.md)
