---
title: "IMetaDataImport::ResolveTypeRef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.ResolveTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 390387abef5c48b4842adcfbfca126bb8292cc28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="d91e1-102">IMetaDataImport::ResolveTypeRef 方法</span><span class="sxs-lookup"><span data-stu-id="d91e1-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="d91e1-103">解析<xref:System.Type>指定的 TypeRef 标记所表示的引用。</span><span class="sxs-lookup"><span data-stu-id="d91e1-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d91e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="d91e1-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d91e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="d91e1-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="d91e1-106">[in]要返回的引用的类型信息的 TypeRef 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d91e1-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="d91e1-107">[in]接口的 IID，以返回`ppIScope`。</span><span class="sxs-lookup"><span data-stu-id="d91e1-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="d91e1-108">通常，这是 IID_IMetaDataImport。</span><span class="sxs-lookup"><span data-stu-id="d91e1-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="d91e1-109">[out]一个指向在其中定义引用的类型的模块作用域接口。</span><span class="sxs-lookup"><span data-stu-id="d91e1-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="d91e1-110">[out]指向表示引用的类型的 TypeDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="d91e1-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d91e1-111">备注</span><span class="sxs-lookup"><span data-stu-id="d91e1-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d91e1-112">如果加载多个应用程序域，则不要使用此方法。</span><span class="sxs-lookup"><span data-stu-id="d91e1-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="d91e1-113">该方法不遵从应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="d91e1-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="d91e1-114">如果已加载的程序集的多个版本，并且它们包含具有相同的命名空间的相同类型，该方法将返回它找到的第一个类型的模块作用域。</span><span class="sxs-lookup"><span data-stu-id="d91e1-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="d91e1-115">`ResolveTypeRef`方法搜索其他模块中的类型定义。</span><span class="sxs-lookup"><span data-stu-id="d91e1-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="d91e1-116">如果找到的类型定义，则`ResolveTypeRef`返回一个指向该模块作用域，以及该类型的 TypeDef 标记接口。</span><span class="sxs-lookup"><span data-stu-id="d91e1-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="d91e1-117">如果要将解析的类型引用具有 AssemblyRef，解析范围`ResolveTypeRef`方法搜索仅中已经打开与调用的元数据作用域的匹配项[imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法或[imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d91e1-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="d91e1-118">这是因为`ResolveTypeRef`无法确定从仅在磁盘上或在全局程序集缓存中程序集的存储位置的 AssemblyRef 作用域。</span><span class="sxs-lookup"><span data-stu-id="d91e1-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d91e1-119">要求</span><span class="sxs-lookup"><span data-stu-id="d91e1-119">Requirements</span></span>  
 <span data-ttu-id="d91e1-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d91e1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d91e1-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d91e1-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d91e1-122">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d91e1-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d91e1-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d91e1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91e1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d91e1-124">See Also</span></span>  
 [<span data-ttu-id="d91e1-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d91e1-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d91e1-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d91e1-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
