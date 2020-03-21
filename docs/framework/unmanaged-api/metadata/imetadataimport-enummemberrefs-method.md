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
ms.openlocfilehash: b8a65b0748fec0e474d8b3b5dc03473fbd716108
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177337"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="8af14-102">IMetaDataImport::EnumMemberRefs 方法</span><span class="sxs-lookup"><span data-stu-id="8af14-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="8af14-103">枚举表示指定类型成员的 MemberRef 标记。</span><span class="sxs-lookup"><span data-stu-id="8af14-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af14-104">语法</span><span class="sxs-lookup"><span data-stu-id="8af14-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8af14-105">parameters</span><span class="sxs-lookup"><span data-stu-id="8af14-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8af14-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="8af14-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="8af14-107">[在]要枚举其成员的类型的类型的类型类型，TypeDef、TypeRef、方法Def或 ModuleRef 令牌。</span><span class="sxs-lookup"><span data-stu-id="8af14-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="8af14-108">[出]用于存储会员Ref令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="8af14-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8af14-109">[in] `rMemberRefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="8af14-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8af14-110">[出]在 中`rMemberRefs`返回的会员Ref 令牌的实际数量。</span><span class="sxs-lookup"><span data-stu-id="8af14-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8af14-111">返回值</span><span class="sxs-lookup"><span data-stu-id="8af14-111">Return Value</span></span>  
  
|<span data-ttu-id="8af14-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8af14-112">HRESULT</span></span>|<span data-ttu-id="8af14-113">说明</span><span class="sxs-lookup"><span data-stu-id="8af14-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8af14-114">`EnumMemberRefs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8af14-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8af14-115">没有要枚举的会员Ref令牌。</span><span class="sxs-lookup"><span data-stu-id="8af14-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="8af14-116">在这种情况下，`pcTokens`是零。</span><span class="sxs-lookup"><span data-stu-id="8af14-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8af14-117">要求</span><span class="sxs-lookup"><span data-stu-id="8af14-117">Requirements</span></span>  
 <span data-ttu-id="8af14-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8af14-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af14-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="8af14-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8af14-120">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="8af14-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8af14-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af14-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af14-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8af14-122">See also</span></span>

- [<span data-ttu-id="8af14-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="8af14-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8af14-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="8af14-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
