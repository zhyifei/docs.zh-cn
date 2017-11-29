---
title: "IMetaDataImport::FindField 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2178f8738ca510fb2163c1043dd94ebcb7043904
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="bc5ab-102">IMetaDataImport::FindField 方法</span><span class="sxs-lookup"><span data-stu-id="bc5ab-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="bc5ab-103">获取指向与 FieldDef 标记为包含该字段指定<xref:System.Type>并具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc5ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc5ab-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc5ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="bc5ab-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bc5ab-106">[in]对类或接口包含要搜索的字段的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="bc5ab-107">如果此值为`mdTokenNil`，对全局变量执行查找。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="bc5ab-108">[in]要搜索的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bc5ab-109">[in]指向该字段的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bc5ab-110">[in]以字节为单位的大小`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="bc5ab-111">[out]指向匹配的 FieldDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc5ab-112">备注</span><span class="sxs-lookup"><span data-stu-id="bc5ab-112">Remarks</span></span>  
 <span data-ttu-id="bc5ab-113">指定使用其封闭类或接口的字段 (`td`)，其名称 (`szName`)，（可选） 及其签名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="bc5ab-114">签名传递给`FindField`必须已生成在当前范围内，因为签名绑定到特定的作用域。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="bc5ab-115">签名中可以嵌入标识封闭类或值类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="bc5ab-116">（该标记是本地的 TypeDef 表中的索引）。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="bc5ab-117">无法生成上下文之外的当前作用域的运行时签名并使用该签名作为输入`FindField`。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="bc5ab-118">`FindField`查找直接在类或接口; 中定义的字段找不到继承的所有字段。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc5ab-119">要求</span><span class="sxs-lookup"><span data-stu-id="bc5ab-119">Requirements</span></span>  
 <span data-ttu-id="bc5ab-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc5ab-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc5ab-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bc5ab-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc5ab-122">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bc5ab-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc5ab-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc5ab-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5ab-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc5ab-124">See Also</span></span>  
 [<span data-ttu-id="bc5ab-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="bc5ab-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="bc5ab-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="bc5ab-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
