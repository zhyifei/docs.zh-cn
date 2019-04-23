---
title: IMetaDataImport::EnumPermissionSets 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28e6ad309af808638400fc27255acdee381b4c6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196692"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="d339a-102">IMetaDataImport::EnumPermissionSets 方法</span><span class="sxs-lookup"><span data-stu-id="d339a-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="d339a-103">枚举指定的元数据范围内的对象的权限。</span><span class="sxs-lookup"><span data-stu-id="d339a-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d339a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d339a-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d339a-105">参数</span><span class="sxs-lookup"><span data-stu-id="d339a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d339a-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="d339a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d339a-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d339a-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="d339a-108">[in]元数据标记，用于限制搜索，或者为 NULL 以搜索可能的范围最大作用域。</span><span class="sxs-lookup"><span data-stu-id="d339a-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="d339a-109">[in]标志表示<xref:System.Security.Permissions.SecurityAction>值时要包含在`rPermission`，或为零，则返回的所有操作。</span><span class="sxs-lookup"><span data-stu-id="d339a-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="d339a-110">[out]用于存储权限令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="d339a-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d339a-111">[in] `rPermission` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="d339a-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d339a-112">[out]权限令牌中返回的数`rPermission`。</span><span class="sxs-lookup"><span data-stu-id="d339a-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d339a-113">返回值</span><span class="sxs-lookup"><span data-stu-id="d339a-113">Return Value</span></span>  
  
|<span data-ttu-id="d339a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d339a-114">HRESULT</span></span>|<span data-ttu-id="d339a-115">描述</span><span class="sxs-lookup"><span data-stu-id="d339a-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d339a-116">`EnumPermissionSets` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d339a-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d339a-117">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="d339a-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="d339a-118">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="d339a-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d339a-119">要求</span><span class="sxs-lookup"><span data-stu-id="d339a-119">Requirements</span></span>  
 <span data-ttu-id="d339a-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d339a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d339a-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d339a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d339a-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d339a-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d339a-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d339a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d339a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d339a-124">See also</span></span>

- [<span data-ttu-id="d339a-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d339a-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d339a-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d339a-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
