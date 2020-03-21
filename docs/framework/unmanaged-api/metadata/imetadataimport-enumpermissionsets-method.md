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
ms.openlocfilehash: e628cf5dab8006b0df0ab6c60dc995cd0c6bb29d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175442"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="d60e3-102">IMetaDataImport::EnumPermissionSets 方法</span><span class="sxs-lookup"><span data-stu-id="d60e3-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="d60e3-103">枚举指定的元数据范围内的对象的权限。</span><span class="sxs-lookup"><span data-stu-id="d60e3-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="d60e3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d60e3-105">parameters</span><span class="sxs-lookup"><span data-stu-id="d60e3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d60e3-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="d60e3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d60e3-107">对于此方法的第一次调用，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d60e3-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="d60e3-108">[在]限制搜索范围的元数据令牌，或 NULL 以搜索尽可能广泛的范围。</span><span class="sxs-lookup"><span data-stu-id="d60e3-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="d60e3-109">[在]表示 要<xref:System.Security.Permissions.SecurityAction>包括在 中`rPermission`的值的标志，或零以返回所有操作。</span><span class="sxs-lookup"><span data-stu-id="d60e3-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="d60e3-110">[出]用于存储权限令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="d60e3-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d60e3-111">[in] `rPermission` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="d60e3-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d60e3-112">[出]在 中`rPermission`返回的权限令牌数。</span><span class="sxs-lookup"><span data-stu-id="d60e3-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d60e3-113">返回值</span><span class="sxs-lookup"><span data-stu-id="d60e3-113">Return Value</span></span>  
  
|<span data-ttu-id="d60e3-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d60e3-114">HRESULT</span></span>|<span data-ttu-id="d60e3-115">说明</span><span class="sxs-lookup"><span data-stu-id="d60e3-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d60e3-116">`EnumPermissionSets`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d60e3-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d60e3-117">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="d60e3-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="d60e3-118">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="d60e3-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d60e3-119">要求</span><span class="sxs-lookup"><span data-stu-id="d60e3-119">Requirements</span></span>  
 <span data-ttu-id="d60e3-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d60e3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d60e3-121">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="d60e3-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d60e3-122">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="d60e3-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d60e3-123">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d60e3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60e3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d60e3-124">See also</span></span>

- [<span data-ttu-id="d60e3-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d60e3-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d60e3-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d60e3-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
