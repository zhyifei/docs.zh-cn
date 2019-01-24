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
ms.openlocfilehash: b47369e8cee2215b3e7a21e9f069d18dffda847a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691734"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="b10f6-102">IMetaDataImport::FindTypeRef 方法</span><span class="sxs-lookup"><span data-stu-id="b10f6-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="b10f6-103">获取一个指向 TypeRef 标记，表示<xref:System.Type>指定作用域中并具有指定的名称的引用。</span><span class="sxs-lookup"><span data-stu-id="b10f6-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b10f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="b10f6-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b10f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="b10f6-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="b10f6-106">[in]ModuleRef、 AssemblyRef 或 TypeRef 标记，用于指定模块、 程序集或类型，分别在它们引用类型定义。</span><span class="sxs-lookup"><span data-stu-id="b10f6-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="b10f6-107">[in]要搜索的类型引用的名称。</span><span class="sxs-lookup"><span data-stu-id="b10f6-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="b10f6-108">[out]指向匹配的 TypeRef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="b10f6-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b10f6-109">要求</span><span class="sxs-lookup"><span data-stu-id="b10f6-109">Requirements</span></span>  
 <span data-ttu-id="b10f6-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b10f6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b10f6-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b10f6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b10f6-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b10f6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b10f6-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b10f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b10f6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b10f6-114">See also</span></span>
- [<span data-ttu-id="b10f6-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="b10f6-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b10f6-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="b10f6-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
