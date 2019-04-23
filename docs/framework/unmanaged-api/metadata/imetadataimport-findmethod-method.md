---
title: IMetaDataImport::FindMethod 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28aa8313e7ba0c071187d0f1f6d78431b16fc005
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164796"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="3fcb2-102">IMetaDataImport::FindMethod 方法</span><span class="sxs-lookup"><span data-stu-id="3fcb2-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="3fcb2-103">获取指向 MethodDef 标记所用的方法由指定<xref:System.Type>并具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fcb2-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fcb2-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fcb2-105">参数</span><span class="sxs-lookup"><span data-stu-id="3fcb2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3fcb2-106">[in]`mdTypeDef`标记，表示包含要搜索的成员的类型 （类或接口）。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="3fcb2-107">如果此值为`mdTokenNil`，则会对全局函数执行查找。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="3fcb2-108">[in]要搜索的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="3fcb2-109">[in]指向方法的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="3fcb2-110">[in]以字节为单位的大小`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="3fcb2-111">[out]指向匹配的 MethodDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fcb2-112">备注</span><span class="sxs-lookup"><span data-stu-id="3fcb2-112">Remarks</span></span>  
 <span data-ttu-id="3fcb2-113">指定使用封闭类或接口的方法 (`td`)，其名称 (`szName`)，并根据需要它的签名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="3fcb2-114">可能有多个具有相同名称的类或接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="3fcb2-115">在这种情况下，传递方法的签名，以查找唯一匹配项。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="3fcb2-116">签名传递给`FindMethod`必须已生成在当前范围内，因为这些签名将绑定到特定的作用域。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="3fcb2-117">签名可以嵌入令牌，用于标识封闭类或值类型。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="3fcb2-118">令牌的本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="3fcb2-119">不能生成上下文的当前作用域外部的运行时签名并使用该签名一样的输入`FindMethod`。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="3fcb2-120">`FindMethod` 查找直接在类或接口; 中定义的方法找不到继承的方法。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fcb2-121">要求</span><span class="sxs-lookup"><span data-stu-id="3fcb2-121">Requirements</span></span>  
 <span data-ttu-id="3fcb2-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fcb2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fcb2-123">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3fcb2-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3fcb2-124">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3fcb2-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3fcb2-125">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fcb2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fcb2-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fcb2-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="3fcb2-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3fcb2-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3fcb2-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3fcb2-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
