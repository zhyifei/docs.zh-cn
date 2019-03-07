---
title: IMetaDataImport::FindField 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a6f2e428366d2fe96313879ef1256d7b86ddd29
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490406"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="48060-102">IMetaDataImport::FindField 方法</span><span class="sxs-lookup"><span data-stu-id="48060-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="48060-103">获取指向 FieldDef 标记字段包含由指定<xref:System.Type>并具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="48060-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48060-104">语法</span><span class="sxs-lookup"><span data-stu-id="48060-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48060-105">参数</span><span class="sxs-lookup"><span data-stu-id="48060-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="48060-106">[in]对类或接口，包含要搜索的字段的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="48060-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="48060-107">如果此值为`mdTokenNil`，在执行查找的全局变量。</span><span class="sxs-lookup"><span data-stu-id="48060-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="48060-108">[in]要搜索的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="48060-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="48060-109">[in]一个指向该字段的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="48060-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="48060-110">[in]以字节为单位的大小`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="48060-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="48060-111">[out]指向匹配的 FieldDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="48060-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48060-112">备注</span><span class="sxs-lookup"><span data-stu-id="48060-112">Remarks</span></span>  
 <span data-ttu-id="48060-113">指定使用封闭类或接口的字段 (`td`)，其名称 (`szName`)，并根据需要它的签名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="48060-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="48060-114">签名传递给`FindField`必须已生成在当前范围内，因为这些签名将绑定到特定的作用域。</span><span class="sxs-lookup"><span data-stu-id="48060-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="48060-115">签名可以嵌入令牌，用于标识封闭类或值类型。</span><span class="sxs-lookup"><span data-stu-id="48060-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="48060-116">（该标记是本地的 TypeDef 表中的索引）。</span><span class="sxs-lookup"><span data-stu-id="48060-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="48060-117">无法生成上下文的当前作用域外部的运行时签名并使用该签名作为输入`FindField`。</span><span class="sxs-lookup"><span data-stu-id="48060-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="48060-118">`FindField` 查找直接在类或接口; 中定义的字段找不到继承的字段。</span><span class="sxs-lookup"><span data-stu-id="48060-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48060-119">要求</span><span class="sxs-lookup"><span data-stu-id="48060-119">Requirements</span></span>  
 <span data-ttu-id="48060-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48060-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48060-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="48060-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48060-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="48060-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48060-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48060-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48060-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="48060-124">See also</span></span>
- [<span data-ttu-id="48060-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="48060-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="48060-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="48060-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
