---
title: IMetaDataImport::ResolveTypeRef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f929e6b338d4fd48b2a6ef9588523377e0dd8faa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096057"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="eda1f-102">IMetaDataImport::ResolveTypeRef 方法</span><span class="sxs-lookup"><span data-stu-id="eda1f-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="eda1f-103">解析<xref:System.Type>指定的 TypeRef 标记所表示的引用。</span><span class="sxs-lookup"><span data-stu-id="eda1f-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eda1f-104">语法</span><span class="sxs-lookup"><span data-stu-id="eda1f-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eda1f-105">参数</span><span class="sxs-lookup"><span data-stu-id="eda1f-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="eda1f-106">[in]要返回的被引用的类型信息的 TypeRef 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="eda1f-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="eda1f-107">[in]若要在中返回的接口的 IID `ppIScope`。</span><span class="sxs-lookup"><span data-stu-id="eda1f-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="eda1f-108">通常情况下，这将是 IID_IMetaDataImport。</span><span class="sxs-lookup"><span data-stu-id="eda1f-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="eda1f-109">[out]一个要在其中定义被引用的类型在模块作用域的接口。</span><span class="sxs-lookup"><span data-stu-id="eda1f-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="eda1f-110">[out]指向表示被引用的类型的 TypeDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="eda1f-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eda1f-111">备注</span><span class="sxs-lookup"><span data-stu-id="eda1f-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eda1f-112">如果加载多个应用程序域，则不使用此方法。</span><span class="sxs-lookup"><span data-stu-id="eda1f-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="eda1f-113">该方法不会接受应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="eda1f-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="eda1f-114">如果加载了多个版本的程序集，并且它们包含具有相同的命名空间的相同类型，该方法将返回它找到的第一个类型在模块作用域。</span><span class="sxs-lookup"><span data-stu-id="eda1f-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="eda1f-115">`ResolveTypeRef`方法搜索的其他模块中的类型定义。</span><span class="sxs-lookup"><span data-stu-id="eda1f-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="eda1f-116">如果找到该类型定义，则`ResolveTypeRef`返回一个指向该模块作用域，以及类型的 TypeDef 标记接口。</span><span class="sxs-lookup"><span data-stu-id="eda1f-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="eda1f-117">如果要将解析的类型引用具有 AssemblyRef，解析范围`ResolveTypeRef`方法搜索匹配项仅在已打开与调用的元数据作用域中[imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法或[imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="eda1f-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="eda1f-118">这是因为`ResolveTypeRef`无法确定从磁盘上或位于全局程序集缓存程序集的存储位置的 AssemblyRef 范围。</span><span class="sxs-lookup"><span data-stu-id="eda1f-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eda1f-119">要求</span><span class="sxs-lookup"><span data-stu-id="eda1f-119">Requirements</span></span>  
 <span data-ttu-id="eda1f-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eda1f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eda1f-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eda1f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eda1f-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eda1f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="eda1f-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="eda1f-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eda1f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="eda1f-124">See also</span></span>

- [<span data-ttu-id="eda1f-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="eda1f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eda1f-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="eda1f-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
