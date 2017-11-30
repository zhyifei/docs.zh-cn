---
title: "IMetaDataImport::EnumMemberRefs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMemberRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9a47d723aaf7dd83bc488a07b040b43a206be55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="b515d-102">IMetaDataImport::EnumMemberRefs 方法</span><span class="sxs-lookup"><span data-stu-id="b515d-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="b515d-103">枚举表示指定类型成员的 MemberRef 标记。</span><span class="sxs-lookup"><span data-stu-id="b515d-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b515d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b515d-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b515d-105">参数</span><span class="sxs-lookup"><span data-stu-id="b515d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b515d-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="b515d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="b515d-107">[in]要枚举其成员的类型 TypeDef、 TypeRef、 MethodDef 或 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="b515d-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="b515d-108">[out]用于存储 MemberRef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="b515d-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b515d-109">[in] `rMemberRefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="b515d-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b515d-110">[out]在中返回的 MemberRef 标记的实际数`rMemberRefs`。</span><span class="sxs-lookup"><span data-stu-id="b515d-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b515d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b515d-111">Return Value</span></span>  
  
|<span data-ttu-id="b515d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b515d-112">HRESULT</span></span>|<span data-ttu-id="b515d-113">描述</span><span class="sxs-lookup"><span data-stu-id="b515d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b515d-114">`EnumMemberRefs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b515d-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b515d-115">没有要枚举的 MemberRef 标记。</span><span class="sxs-lookup"><span data-stu-id="b515d-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="b515d-116">在这种情况下，`pcTokens`将为零。</span><span class="sxs-lookup"><span data-stu-id="b515d-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b515d-117">要求</span><span class="sxs-lookup"><span data-stu-id="b515d-117">Requirements</span></span>  
 <span data-ttu-id="b515d-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b515d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b515d-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b515d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b515d-120">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b515d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b515d-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b515d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b515d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b515d-122">See Also</span></span>  
 [<span data-ttu-id="b515d-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="b515d-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b515d-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="b515d-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
