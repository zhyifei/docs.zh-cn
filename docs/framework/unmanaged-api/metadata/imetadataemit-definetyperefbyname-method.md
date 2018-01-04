---
title: "IMetaDataEmit::DefineTypeRefByName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46b9fe83a5beb031d4ac21deb903060e2f788e1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="7cf33-102">IMetaDataEmit::DefineTypeRefByName 方法</span><span class="sxs-lookup"><span data-stu-id="7cf33-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="7cf33-103">获取定义在指定范围内，这是当前作用域之外的类型元数据标记。</span><span class="sxs-lookup"><span data-stu-id="7cf33-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf33-104">语法</span><span class="sxs-lookup"><span data-stu-id="7cf33-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7cf33-105">参数</span><span class="sxs-lookup"><span data-stu-id="7cf33-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="7cf33-106">[in]指定解析范围令牌。</span><span class="sxs-lookup"><span data-stu-id="7cf33-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="7cf33-107">以下令牌类型为有效值：</span><span class="sxs-lookup"><span data-stu-id="7cf33-107">The following token types are valid:</span></span>  
  
-   <span data-ttu-id="7cf33-108">`mdModuleRef`如果在其中定义调用方位于同一程序集中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="7cf33-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="7cf33-109">`mdAssemblyRef`如果在不是在其中定义调用方的程序集中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="7cf33-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="7cf33-110">`mdTypeRef`如果该类型是嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="7cf33-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
-   <span data-ttu-id="7cf33-111">`mdModule`如果在其中定义调用方的相同模块中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="7cf33-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="7cf33-112">如果全局定义的类型，则为 null。</span><span class="sxs-lookup"><span data-stu-id="7cf33-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="7cf33-113">[in]Unicode 中的目标类型的名称。</span><span class="sxs-lookup"><span data-stu-id="7cf33-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="7cf33-114">[out]指向的指针`mdTypeRef`分配给类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="7cf33-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf33-115">惠?</span><span class="sxs-lookup"><span data-stu-id="7cf33-115">Requirements</span></span>  
 <span data-ttu-id="7cf33-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7cf33-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf33-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7cf33-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cf33-118">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7cf33-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cf33-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf33-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf33-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cf33-120">See Also</span></span>  
 [<span data-ttu-id="7cf33-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="7cf33-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7cf33-122">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="7cf33-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
