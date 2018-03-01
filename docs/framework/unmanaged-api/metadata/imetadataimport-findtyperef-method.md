---
title: "IMetaDataImport::FindTypeRef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3321f8ea1897f807a06d5c9a812fded2fd7f6365
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="fdbe9-102">IMetaDataImport::FindTypeRef 方法</span><span class="sxs-lookup"><span data-stu-id="fdbe9-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="fdbe9-103">获取一个指向 TypeRef 标记，表示<xref:System.Type>中指定的作用域并具有指定的名称的引用。</span><span class="sxs-lookup"><span data-stu-id="fdbe9-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdbe9-104">语法</span><span class="sxs-lookup"><span data-stu-id="fdbe9-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdbe9-105">参数</span><span class="sxs-lookup"><span data-stu-id="fdbe9-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="fdbe9-106">[in]指定模块、 程序集或类型的 ModuleRef、 AssemblyRef 或 TypeRef 令牌分别在类型引用该定义。</span><span class="sxs-lookup"><span data-stu-id="fdbe9-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="fdbe9-107">[in]要搜索的类型引用的名称。</span><span class="sxs-lookup"><span data-stu-id="fdbe9-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="fdbe9-108">[out]指向匹配的 TypeRef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="fdbe9-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdbe9-109">惠?</span><span class="sxs-lookup"><span data-stu-id="fdbe9-109">Requirements</span></span>  
 <span data-ttu-id="fdbe9-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fdbe9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdbe9-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fdbe9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fdbe9-112">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fdbe9-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fdbe9-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdbe9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdbe9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdbe9-114">See Also</span></span>  
 [<span data-ttu-id="fdbe9-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="fdbe9-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="fdbe9-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="fdbe9-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
