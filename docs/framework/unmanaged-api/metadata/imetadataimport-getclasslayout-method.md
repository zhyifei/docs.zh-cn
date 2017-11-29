---
title: "IMetaDataImport::GetClassLayout 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cece37a6321fc68cbff2957f9753af5f2f916f5f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="9fdf6-102">IMetaDataImport::GetClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="9fdf6-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="9fdf6-103">获取指定的 TypeDef 标记所引用类的布局信息。</span><span class="sxs-lookup"><span data-stu-id="9fdf6-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fdf6-104">语法</span><span class="sxs-lookup"><span data-stu-id="9fdf6-104">Syntax</span></span>  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fdf6-105">参数</span><span class="sxs-lookup"><span data-stu-id="9fdf6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9fdf6-106">[in]具有要返回的布局的类 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="9fdf6-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="9fdf6-107">[out]值 1、 2、 4、 8 或 16，表示类的包大小之一。</span><span class="sxs-lookup"><span data-stu-id="9fdf6-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="9fdf6-108">[out]数组[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)值。</span><span class="sxs-lookup"><span data-stu-id="9fdf6-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9fdf6-109">[in] `rFieldOffset` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="9fdf6-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="9fdf6-110">[out]在中返回的元素的数目`rFieldOffset`。</span><span class="sxs-lookup"><span data-stu-id="9fdf6-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="9fdf6-111">[out]以字节为单位的所表示的类的大小`td`。</span><span class="sxs-lookup"><span data-stu-id="9fdf6-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fdf6-112">要求</span><span class="sxs-lookup"><span data-stu-id="9fdf6-112">Requirements</span></span>  
 <span data-ttu-id="9fdf6-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9fdf6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fdf6-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9fdf6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9fdf6-115">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9fdf6-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9fdf6-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fdf6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fdf6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fdf6-117">See Also</span></span>  
 [<span data-ttu-id="9fdf6-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="9fdf6-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9fdf6-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="9fdf6-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
