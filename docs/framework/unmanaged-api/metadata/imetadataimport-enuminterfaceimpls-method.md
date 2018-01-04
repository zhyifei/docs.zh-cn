---
title: "IMetaDataImport::EnumInterfaceImpls 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumInterfaceImpls
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 646d65ff81795ce0558651db9c3fe1bc7205ae08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="df8bf-102">IMetaDataImport::EnumInterfaceImpls 方法</span><span class="sxs-lookup"><span data-stu-id="df8bf-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="df8bf-103">枚举表示接口实现的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="df8bf-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df8bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="df8bf-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df8bf-105">参数</span><span class="sxs-lookup"><span data-stu-id="df8bf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="df8bf-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="df8bf-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="df8bf-107">[in]表示接口实现的 MethodDef 标记是要枚举的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="df8bf-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="df8bf-108">[out]用于存储的 MethodDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="df8bf-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="df8bf-109">[in] `rImpls` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="df8bf-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="df8bf-110">[out]令牌中返回的实际数目`rImpls`。</span><span class="sxs-lookup"><span data-stu-id="df8bf-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df8bf-111">返回值</span><span class="sxs-lookup"><span data-stu-id="df8bf-111">Return Value</span></span>  
  
|<span data-ttu-id="df8bf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df8bf-112">HRESULT</span></span>|<span data-ttu-id="df8bf-113">描述</span><span class="sxs-lookup"><span data-stu-id="df8bf-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="df8bf-114">`EnumInterfaceImpls`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="df8bf-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="df8bf-115">没有要枚举的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="df8bf-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="df8bf-116">在这种情况下，`pcImpls`设置为零。</span><span class="sxs-lookup"><span data-stu-id="df8bf-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df8bf-117">惠?</span><span class="sxs-lookup"><span data-stu-id="df8bf-117">Requirements</span></span>  
 <span data-ttu-id="df8bf-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df8bf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df8bf-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="df8bf-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df8bf-120">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="df8bf-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df8bf-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df8bf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df8bf-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="df8bf-122">See Also</span></span>  
 [<span data-ttu-id="df8bf-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="df8bf-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="df8bf-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="df8bf-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
