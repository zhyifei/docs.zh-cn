---
title: IMetaDataEmit::DefineTypeRefByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: 23a6931b31ea2d7e4e8d1cb3dc8adf3a51216315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175741"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="a5b28-102">IMetaDataEmit::DefineTypeRefByName 方法</span><span class="sxs-lookup"><span data-stu-id="a5b28-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="a5b28-103">获取在指定作用域中定义的类型的元数据令牌，该类型在当前作用域之外。</span><span class="sxs-lookup"><span data-stu-id="a5b28-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b28-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5b28-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5b28-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a5b28-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="a5b28-106">[在]指定解析作用域的令牌。</span><span class="sxs-lookup"><span data-stu-id="a5b28-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="a5b28-107">以下令牌类型有效：</span><span class="sxs-lookup"><span data-stu-id="a5b28-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="a5b28-108">`mdModuleRef`，如果类型是在定义调用方的同一程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="a5b28-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="a5b28-109">`mdAssemblyRef`，如果类型是在定义调用方的程序集以外的程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="a5b28-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="a5b28-110">`mdTypeRef`，如果类型是嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="a5b28-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="a5b28-111">`mdModule`，如果类型是在定义调用方的同一模块中定义的。</span><span class="sxs-lookup"><span data-stu-id="a5b28-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="a5b28-112">如果类型是全局定义的，则为 null。</span><span class="sxs-lookup"><span data-stu-id="a5b28-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="a5b28-113">[在]Unicode 中的目标类型的名称。</span><span class="sxs-lookup"><span data-stu-id="a5b28-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="a5b28-114">[出]指向分配给类型的`mdTypeRef`令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="a5b28-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b28-115">要求</span><span class="sxs-lookup"><span data-stu-id="a5b28-115">Requirements</span></span>  
 <span data-ttu-id="a5b28-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5b28-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5b28-117">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a5b28-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5b28-118">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a5b28-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5b28-119">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5b28-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b28-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5b28-120">See also</span></span>

- [<span data-ttu-id="a5b28-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="a5b28-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a5b28-122">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="a5b28-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
