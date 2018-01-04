---
title: "IMetaDataEmit::DefinePermissionSet 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefinePermissionSet
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74bea316d3f56e007c4b75e6b801d8c82ae8ce96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="ab8be-102">IMetaDataEmit::DefinePermissionSet 方法</span><span class="sxs-lookup"><span data-stu-id="ab8be-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="ab8be-103">创建一个定义为权限集与指定的元数据签名，并获取该权限集定义的标记。</span><span class="sxs-lookup"><span data-stu-id="ab8be-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab8be-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab8be-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab8be-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab8be-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ab8be-106">[in]要修饰的对象。</span><span class="sxs-lookup"><span data-stu-id="ab8be-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="ab8be-107">[in]A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)值，该值指定要使用的声明性安全的类型。</span><span class="sxs-lookup"><span data-stu-id="ab8be-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="ab8be-108">[in]BLOB 的权限。</span><span class="sxs-lookup"><span data-stu-id="ab8be-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="ab8be-109">[in]大小，以字节为单位的`pvPermission`。</span><span class="sxs-lookup"><span data-stu-id="ab8be-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="ab8be-110">[out]返回的权限标记中。</span><span class="sxs-lookup"><span data-stu-id="ab8be-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab8be-111">惠?</span><span class="sxs-lookup"><span data-stu-id="ab8be-111">Requirements</span></span>  
 <span data-ttu-id="ab8be-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab8be-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab8be-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ab8be-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab8be-114">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ab8be-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab8be-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab8be-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab8be-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab8be-116">See Also</span></span>  
 [<span data-ttu-id="ab8be-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="ab8be-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ab8be-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="ab8be-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
