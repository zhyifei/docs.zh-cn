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
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177255"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="77ae8-102">IMetaDataImport::FindMethod 方法</span><span class="sxs-lookup"><span data-stu-id="77ae8-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="77ae8-103">获取指向方法的指针，该方法由指定内容<xref:System.Type>封闭，并且具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="77ae8-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77ae8-104">语法</span><span class="sxs-lookup"><span data-stu-id="77ae8-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77ae8-105">parameters</span><span class="sxs-lookup"><span data-stu-id="77ae8-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="77ae8-106">[在]包含`mdTypeDef`要搜索的成员的类型（类或接口）的令牌。</span><span class="sxs-lookup"><span data-stu-id="77ae8-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="77ae8-107">如果此值为`mdTokenNil`，则对全局函数执行查找。</span><span class="sxs-lookup"><span data-stu-id="77ae8-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="77ae8-108">[在]要搜索的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="77ae8-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="77ae8-109">[在]指向方法的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="77ae8-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="77ae8-110">[在]的大小（以字节为单位）。 `pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="77ae8-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="77ae8-111">[出]指向匹配的 MethodDef 令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="77ae8-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77ae8-112">备注</span><span class="sxs-lookup"><span data-stu-id="77ae8-112">Remarks</span></span>  
 <span data-ttu-id="77ae8-113">使用其封闭类或接口 （））`td``szName`和可选方式指定方法的签名 （）。`pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="77ae8-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="77ae8-114">类或接口中可能有多个同名方法。</span><span class="sxs-lookup"><span data-stu-id="77ae8-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="77ae8-115">在这种情况下，传递方法的签名以查找唯一匹配项。</span><span class="sxs-lookup"><span data-stu-id="77ae8-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="77ae8-116">传递给的签名`FindMethod`必须在当前作用域中生成，因为签名绑定到特定作用域。</span><span class="sxs-lookup"><span data-stu-id="77ae8-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="77ae8-117">签名可以嵌入标识封闭类或值类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="77ae8-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="77ae8-118">令牌是本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="77ae8-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="77ae8-119">不能在当前作用域的上下文之外生成运行时签名，并且使用该签名作为输入 到`FindMethod`的输入。</span><span class="sxs-lookup"><span data-stu-id="77ae8-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="77ae8-120">`FindMethod`仅查找直接在类或接口中定义的方法;它找不到继承的方法。</span><span class="sxs-lookup"><span data-stu-id="77ae8-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77ae8-121">要求</span><span class="sxs-lookup"><span data-stu-id="77ae8-121">Requirements</span></span>  
 <span data-ttu-id="77ae8-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77ae8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77ae8-123">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="77ae8-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77ae8-124">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="77ae8-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77ae8-125">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77ae8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ae8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77ae8-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="77ae8-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="77ae8-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="77ae8-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="77ae8-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
