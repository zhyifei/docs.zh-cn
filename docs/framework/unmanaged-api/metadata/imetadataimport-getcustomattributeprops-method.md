---
title: "IMetaDataImport::GetCustomAttributeProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetCustomAttributeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 415b1dc67bd3ae3638edd61558cc9e13ebf03fd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="bf08b-102">IMetaDataImport::GetCustomAttributeProps 方法</span><span class="sxs-lookup"><span data-stu-id="bf08b-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="bf08b-103">获取给定元数据标记的自定义属性的值。</span><span class="sxs-lookup"><span data-stu-id="bf08b-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf08b-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf08b-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf08b-105">参数</span><span class="sxs-lookup"><span data-stu-id="bf08b-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="bf08b-106">[in] 表示要检索的自定义属性的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="bf08b-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="bf08b-107">[out, optional] 表示自定义属性修改的对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="bf08b-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="bf08b-108">此值可为任何类型的元数据标记（`mdCustomAttribute` 除外）。</span><span class="sxs-lookup"><span data-stu-id="bf08b-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="bf08b-109">[out, optional] 表示已返回自定义属性的 <xref:System.Type> 的 `mdMethodDef` 或 `mdMemberRef` 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="bf08b-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="bf08b-110">[out, optional] 指向自定义属性的值的数据数组指针。</span><span class="sxs-lookup"><span data-stu-id="bf08b-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="bf08b-111">[out, optional] *`ppBlob` 中返回的数据大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="bf08b-111">[out, optional] The size in bytes of the data returned in *`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf08b-112">备注</span><span class="sxs-lookup"><span data-stu-id="bf08b-112">Remarks</span></span>  
 <span data-ttu-id="bf08b-113">自定义属性以元数据引擎理解的格式存储为数据数组。</span><span class="sxs-lookup"><span data-stu-id="bf08b-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf08b-114">要求</span><span class="sxs-lookup"><span data-stu-id="bf08b-114">Requirements</span></span>  
 <span data-ttu-id="bf08b-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf08b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf08b-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf08b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf08b-117">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bf08b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf08b-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf08b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf08b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf08b-119">See Also</span></span>  
 [<span data-ttu-id="bf08b-120">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="bf08b-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="bf08b-121">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="bf08b-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
