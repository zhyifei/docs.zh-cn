---
title: IMetaDataEmit::DefinePermissionSet 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33eadccf691b14289a46ff460f3cef8ae636b129
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074841"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="0c465-102">IMetaDataEmit::DefinePermissionSet 方法</span><span class="sxs-lookup"><span data-stu-id="0c465-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="0c465-103">创建一个权限集与指定的元数据签名的定义并获取该权限集定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="0c465-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c465-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c465-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c465-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c465-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0c465-106">[in]要进行修饰的对象。</span><span class="sxs-lookup"><span data-stu-id="0c465-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="0c465-107">[in]一个[CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)值，该值指定要使用的声明性安全的类型。</span><span class="sxs-lookup"><span data-stu-id="0c465-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="0c465-108">[in]BLOB 的权限。</span><span class="sxs-lookup"><span data-stu-id="0c465-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="0c465-109">[in]大小，以字节为单位的`pvPermission`。</span><span class="sxs-lookup"><span data-stu-id="0c465-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="0c465-110">[out]返回的权限令牌。</span><span class="sxs-lookup"><span data-stu-id="0c465-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c465-111">要求</span><span class="sxs-lookup"><span data-stu-id="0c465-111">Requirements</span></span>  
 <span data-ttu-id="0c465-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c465-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c465-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c465-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c465-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0c465-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0c465-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0c465-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c465-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c465-116">See also</span></span>

- [<span data-ttu-id="0c465-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="0c465-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0c465-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="0c465-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
