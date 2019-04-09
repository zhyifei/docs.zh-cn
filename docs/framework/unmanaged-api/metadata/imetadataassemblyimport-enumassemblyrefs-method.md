---
title: IMetaDataAssemblyImport::EnumAssemblyRefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91e253669b9f51e7c1d600ba11f13a9ce67fb58a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072475"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="82186-102">IMetaDataAssemblyImport::EnumAssemblyRefs 方法</span><span class="sxs-lookup"><span data-stu-id="82186-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="82186-103">枚举`mdAssemblyRef`的程序集清单中定义的实例。</span><span class="sxs-lookup"><span data-stu-id="82186-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82186-104">语法</span><span class="sxs-lookup"><span data-stu-id="82186-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82186-105">参数</span><span class="sxs-lookup"><span data-stu-id="82186-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="82186-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="82186-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="82186-107">这必须是一个 null 值时`EnumAssemblyRefs`第一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="82186-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="82186-108">[out]枚举`mdAssemblyRef`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="82186-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="82186-109">[in]可以放置在令牌的最大数目`rAssemblyRefs`数组。</span><span class="sxs-lookup"><span data-stu-id="82186-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="82186-110">[out]中实际放置的标记数`rAssemblyRefs`。</span><span class="sxs-lookup"><span data-stu-id="82186-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82186-111">返回值</span><span class="sxs-lookup"><span data-stu-id="82186-111">Return Value</span></span>  
  
|<span data-ttu-id="82186-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82186-112">HRESULT</span></span>|<span data-ttu-id="82186-113">描述</span><span class="sxs-lookup"><span data-stu-id="82186-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` <span data-ttu-id="82186-114">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="82186-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="82186-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="82186-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="82186-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="82186-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82186-117">要求</span><span class="sxs-lookup"><span data-stu-id="82186-117">Requirements</span></span>  
 <span data-ttu-id="82186-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82186-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82186-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="82186-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82186-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="82186-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="82186-121">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="82186-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82186-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="82186-122">See also</span></span>

- [<span data-ttu-id="82186-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="82186-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
