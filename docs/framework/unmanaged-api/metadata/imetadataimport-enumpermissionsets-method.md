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
ms.openlocfilehash: 9d0f443b5b7d2d358534e888c3fc84ad3f554119
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450042"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="7849c-102">IMetaDataImport::EnumPermissionSets 方法</span><span class="sxs-lookup"><span data-stu-id="7849c-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="7849c-103">枚举指定的元数据范围内的对象的权限。</span><span class="sxs-lookup"><span data-stu-id="7849c-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7849c-104">语法</span><span class="sxs-lookup"><span data-stu-id="7849c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7849c-105">参数</span><span class="sxs-lookup"><span data-stu-id="7849c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7849c-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="7849c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7849c-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="7849c-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="7849c-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span><span class="sxs-lookup"><span data-stu-id="7849c-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="7849c-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span><span class="sxs-lookup"><span data-stu-id="7849c-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="7849c-110">[out] The array used to store the Permission tokens.</span><span class="sxs-lookup"><span data-stu-id="7849c-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7849c-111">[in] `rPermission` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7849c-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7849c-112">[out] The number of Permission tokens returned in `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="7849c-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7849c-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7849c-113">Return Value</span></span>  
  
|<span data-ttu-id="7849c-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7849c-114">HRESULT</span></span>|<span data-ttu-id="7849c-115">描述</span><span class="sxs-lookup"><span data-stu-id="7849c-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7849c-116">`EnumPermissionSets` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="7849c-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7849c-117">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="7849c-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="7849c-118">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="7849c-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7849c-119">要求</span><span class="sxs-lookup"><span data-stu-id="7849c-119">Requirements</span></span>  
 <span data-ttu-id="7849c-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7849c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7849c-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7849c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7849c-122">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7849c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7849c-123">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7849c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7849c-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="7849c-124">See also</span></span>

- [<span data-ttu-id="7849c-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7849c-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7849c-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7849c-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
