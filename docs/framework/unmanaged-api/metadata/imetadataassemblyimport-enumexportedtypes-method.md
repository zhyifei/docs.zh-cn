---
title: "IMetaDataAssemblyImport::EnumExportedTypes 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumExportedTypes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54b5a51dc0a12bb4c159b61252c9db0a82f03518
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="0bc58-102">IMetaDataAssemblyImport::EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="0bc58-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="0bc58-103">枚举当前元数据范围内的程序集清单引用的导出的类型。</span><span class="sxs-lookup"><span data-stu-id="0bc58-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bc58-104">语法</span><span class="sxs-lookup"><span data-stu-id="0bc58-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bc58-105">参数</span><span class="sxs-lookup"><span data-stu-id="0bc58-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0bc58-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="0bc58-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0bc58-107">这必须是一个为 null 的值时`EnumExportedTypes`首次调用方法。</span><span class="sxs-lookup"><span data-stu-id="0bc58-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="0bc58-108">[out]枚举`mdExportedType`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="0bc58-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0bc58-109">[in]最大数`mdExportedType`可以放置在令牌`rExportedTypes`数组。</span><span class="sxs-lookup"><span data-stu-id="0bc58-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0bc58-110">[out]数`mdExportedType`令牌实际放入`rExportedTypes`。</span><span class="sxs-lookup"><span data-stu-id="0bc58-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bc58-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0bc58-111">Return Value</span></span>  
  
|<span data-ttu-id="0bc58-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0bc58-112">HRESULT</span></span>|<span data-ttu-id="0bc58-113">描述</span><span class="sxs-lookup"><span data-stu-id="0bc58-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0bc58-114">`EnumExportedTypes`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0bc58-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0bc58-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="0bc58-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="0bc58-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="0bc58-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bc58-117">惠?</span><span class="sxs-lookup"><span data-stu-id="0bc58-117">Requirements</span></span>  
 <span data-ttu-id="0bc58-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bc58-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bc58-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0bc58-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0bc58-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0bc58-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0bc58-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bc58-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc58-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bc58-122">See Also</span></span>  
 [<span data-ttu-id="0bc58-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="0bc58-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
