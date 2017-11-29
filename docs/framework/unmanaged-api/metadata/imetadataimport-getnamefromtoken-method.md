---
title: "IMetaDataImport::GetNameFromToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNameFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e77954d5730417a005c6c1ac07fa171bd0f1b13a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="53f2d-102">IMetaDataImport::GetNameFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="53f2d-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="53f2d-103">获取指定的元数据标记所引用的对象的 UTF-8 名称。</span><span class="sxs-lookup"><span data-stu-id="53f2d-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="53f2d-104">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="53f2d-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f2d-105">语法</span><span class="sxs-lookup"><span data-stu-id="53f2d-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53f2d-106">参数</span><span class="sxs-lookup"><span data-stu-id="53f2d-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="53f2d-107">[in]表示要返回的名称的对象的标记。</span><span class="sxs-lookup"><span data-stu-id="53f2d-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="53f2d-108">[out]指向堆中的 utf-8 对象名称的指针。</span><span class="sxs-lookup"><span data-stu-id="53f2d-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53f2d-109">备注</span><span class="sxs-lookup"><span data-stu-id="53f2d-109">Remarks</span></span>  
 <span data-ttu-id="53f2d-110">`GetNameFromToken` 已过时。</span><span class="sxs-lookup"><span data-stu-id="53f2d-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="53f2d-111">作为替代方法，调用方法，以获取的令牌需要，如的特定类型的属性`GetFieldProps`字段或`GetMethodProps`方法。</span><span class="sxs-lookup"><span data-stu-id="53f2d-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f2d-112">要求</span><span class="sxs-lookup"><span data-stu-id="53f2d-112">Requirements</span></span>  
 <span data-ttu-id="53f2d-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53f2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53f2d-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="53f2d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53f2d-115">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="53f2d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53f2d-116">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="53f2d-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f2d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53f2d-117">See Also</span></span>  
 [<span data-ttu-id="53f2d-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="53f2d-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="53f2d-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="53f2d-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
