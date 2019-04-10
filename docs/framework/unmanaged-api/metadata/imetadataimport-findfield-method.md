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
ms.openlocfilehash: 88cd08b4290739808079bc8ecb713a5c5ea96584
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172557"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="133c6-102">IMetaDataImport::FindField 方法</span><span class="sxs-lookup"><span data-stu-id="133c6-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="133c6-103">获取指向 FieldDef 标记字段包含由指定<xref:System.Type>并具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="133c6-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="133c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="133c6-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="133c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="133c6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="133c6-106">[in]对类或接口，包含要搜索的字段的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="133c6-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="133c6-107">如果此值为`mdTokenNil`，在执行查找的全局变量。</span><span class="sxs-lookup"><span data-stu-id="133c6-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="133c6-108">[in]要搜索的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="133c6-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="133c6-109">[in]一个指向该字段的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="133c6-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="133c6-110">[in]以字节为单位的大小`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="133c6-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="133c6-111">[out]指向匹配的 FieldDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="133c6-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="133c6-112">备注</span><span class="sxs-lookup"><span data-stu-id="133c6-112">Remarks</span></span>  
 <span data-ttu-id="133c6-113">指定使用封闭类或接口的字段 (`td`)，其名称 (`szName`)，并根据需要它的签名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="133c6-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="133c6-114">签名传递给`FindField`必须已生成在当前范围内，因为这些签名将绑定到特定的作用域。</span><span class="sxs-lookup"><span data-stu-id="133c6-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="133c6-115">签名可以嵌入令牌，用于标识封闭类或值类型。</span><span class="sxs-lookup"><span data-stu-id="133c6-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="133c6-116">（该标记是本地的 TypeDef 表中的索引）。</span><span class="sxs-lookup"><span data-stu-id="133c6-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="133c6-117">无法生成上下文的当前作用域外部的运行时签名并使用该签名作为输入`FindField`。</span><span class="sxs-lookup"><span data-stu-id="133c6-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 `FindField` <span data-ttu-id="133c6-118">查找直接在类或接口; 中定义的字段找不到继承的字段。</span><span class="sxs-lookup"><span data-stu-id="133c6-118">finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="133c6-119">要求</span><span class="sxs-lookup"><span data-stu-id="133c6-119">Requirements</span></span>  
 <span data-ttu-id="133c6-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="133c6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="133c6-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="133c6-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="133c6-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="133c6-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="133c6-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="133c6-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="133c6-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="133c6-124">See also</span></span>

- [<span data-ttu-id="133c6-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="133c6-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="133c6-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="133c6-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
