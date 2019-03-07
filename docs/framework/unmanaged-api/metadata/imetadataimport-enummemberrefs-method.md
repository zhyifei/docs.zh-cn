---
title: IMetaDataImport::EnumMemberRefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d73607fc600bf6fbcc2cf831d57a5b4aa740bb09
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498063"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="4dd75-102">IMetaDataImport::EnumMemberRefs 方法</span><span class="sxs-lookup"><span data-stu-id="4dd75-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="4dd75-103">枚举表示指定类型成员的 MemberRef 标记。</span><span class="sxs-lookup"><span data-stu-id="4dd75-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dd75-104">语法</span><span class="sxs-lookup"><span data-stu-id="4dd75-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dd75-105">参数</span><span class="sxs-lookup"><span data-stu-id="4dd75-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4dd75-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="4dd75-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="4dd75-107">[in]要枚举其成员的类型的 TypeDef、 TypeRef、 MethodDef 或 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="4dd75-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="4dd75-108">[out]用于存储 MemberRef 令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="4dd75-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4dd75-109">[in] `rMemberRefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4dd75-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4dd75-110">[out]MemberRef 令牌中返回的实际数目`rMemberRefs`。</span><span class="sxs-lookup"><span data-stu-id="4dd75-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dd75-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4dd75-111">Return Value</span></span>  
  
|<span data-ttu-id="4dd75-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4dd75-112">HRESULT</span></span>|<span data-ttu-id="4dd75-113">描述</span><span class="sxs-lookup"><span data-stu-id="4dd75-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4dd75-114">`EnumMemberRefs` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4dd75-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4dd75-115">没有要枚举的 MemberRef 标记。</span><span class="sxs-lookup"><span data-stu-id="4dd75-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="4dd75-116">在这种情况下，`pcTokens`是为零。</span><span class="sxs-lookup"><span data-stu-id="4dd75-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4dd75-117">要求</span><span class="sxs-lookup"><span data-stu-id="4dd75-117">Requirements</span></span>  
 <span data-ttu-id="4dd75-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4dd75-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dd75-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4dd75-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4dd75-120">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4dd75-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4dd75-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dd75-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd75-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dd75-122">See also</span></span>
- [<span data-ttu-id="4dd75-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="4dd75-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4dd75-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="4dd75-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
