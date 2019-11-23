---
title: IMetaDataEmit::DefineMemberRef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 696389b51328e167212fb2292a873c34b9263811
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431816"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="92253-102">IMetaDataEmit::DefineMemberRef 方法</span><span class="sxs-lookup"><span data-stu-id="92253-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="92253-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span><span class="sxs-lookup"><span data-stu-id="92253-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92253-104">语法</span><span class="sxs-lookup"><span data-stu-id="92253-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92253-105">参数</span><span class="sxs-lookup"><span data-stu-id="92253-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="92253-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span><span class="sxs-lookup"><span data-stu-id="92253-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="92253-107">[in] The name of the target member.</span><span class="sxs-lookup"><span data-stu-id="92253-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="92253-108">[in] The signature of the target member.</span><span class="sxs-lookup"><span data-stu-id="92253-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="92253-109">[in] The count of bytes in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="92253-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="92253-110">[out] The `mdMemberRef` token assigned.</span><span class="sxs-lookup"><span data-stu-id="92253-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92253-111">要求</span><span class="sxs-lookup"><span data-stu-id="92253-111">Requirements</span></span>  
 <span data-ttu-id="92253-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92253-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92253-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92253-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92253-114">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92253-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92253-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92253-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92253-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="92253-116">See also</span></span>

- [<span data-ttu-id="92253-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="92253-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="92253-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="92253-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
