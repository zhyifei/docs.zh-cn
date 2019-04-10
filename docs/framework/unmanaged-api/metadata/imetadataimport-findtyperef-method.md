---
title: IMetaDataImport::FindTypeRef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acc006894f05536ed76bac60b0fde9277a460813
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199019"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="f2327-102">IMetaDataImport::FindTypeRef 方法</span><span class="sxs-lookup"><span data-stu-id="f2327-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="f2327-103">获取一个指向 TypeRef 标记，表示<xref:System.Type>指定作用域中并具有指定的名称的引用。</span><span class="sxs-lookup"><span data-stu-id="f2327-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2327-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2327-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2327-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2327-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="f2327-106">[in]ModuleRef、 AssemblyRef 或 TypeRef 标记，用于指定模块、 程序集或类型，分别在它们引用类型定义。</span><span class="sxs-lookup"><span data-stu-id="f2327-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="f2327-107">[in]要搜索的类型引用的名称。</span><span class="sxs-lookup"><span data-stu-id="f2327-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="f2327-108">[out]指向匹配的 TypeRef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="f2327-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2327-109">要求</span><span class="sxs-lookup"><span data-stu-id="f2327-109">Requirements</span></span>  
 <span data-ttu-id="f2327-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2327-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2327-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2327-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2327-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f2327-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f2327-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f2327-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2327-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2327-114">See also</span></span>

- [<span data-ttu-id="f2327-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f2327-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f2327-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f2327-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
