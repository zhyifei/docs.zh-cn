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
ms.openlocfilehash: 470b6511366cef1680eaf97f9ab376736add55c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437895"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="90cbf-102">IMetaDataImport::FindMethod 方法</span><span class="sxs-lookup"><span data-stu-id="90cbf-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="90cbf-103">获取一个指针，该指针指向方法的 MethodDef 标记，该方法由指定的 <xref:System.Type> 包含并且具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="90cbf-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90cbf-104">语法</span><span class="sxs-lookup"><span data-stu-id="90cbf-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90cbf-105">参数</span><span class="sxs-lookup"><span data-stu-id="90cbf-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="90cbf-106">中包含要搜索的成员的类型（类或接口）的 `mdTypeDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="90cbf-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="90cbf-107">如果 `mdTokenNil`此值，则会对全局函数执行查找。</span><span class="sxs-lookup"><span data-stu-id="90cbf-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="90cbf-108">中要搜索的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="90cbf-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="90cbf-109">中指向方法的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="90cbf-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="90cbf-110">中`pvSigBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="90cbf-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="90cbf-111">弄指向匹配 MethodDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="90cbf-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90cbf-112">备注</span><span class="sxs-lookup"><span data-stu-id="90cbf-112">Remarks</span></span>  
 <span data-ttu-id="90cbf-113">使用方法的封闭类或接口（`td`）、其名称（`szName`）以及可选的签名（`pvSigBlob`）来指定方法。</span><span class="sxs-lookup"><span data-stu-id="90cbf-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="90cbf-114">类或接口中可能有多个具有相同名称的方法。</span><span class="sxs-lookup"><span data-stu-id="90cbf-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="90cbf-115">在这种情况下，传递该方法的签名以查找唯一匹配项。</span><span class="sxs-lookup"><span data-stu-id="90cbf-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="90cbf-116">传递给 `FindMethod` 的签名必须已在当前范围内生成，因为签名将绑定到特定范围。</span><span class="sxs-lookup"><span data-stu-id="90cbf-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="90cbf-117">签名可以嵌入标识封闭类或值类型的标记。</span><span class="sxs-lookup"><span data-stu-id="90cbf-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="90cbf-118">该令牌是本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="90cbf-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="90cbf-119">不能在当前范围的上下文之外生成运行时签名，并使用该签名作为输入 `FindMethod`。</span><span class="sxs-lookup"><span data-stu-id="90cbf-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="90cbf-120">`FindMethod` 仅查找直接在类或接口中定义的方法;它找不到继承的方法。</span><span class="sxs-lookup"><span data-stu-id="90cbf-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90cbf-121">要求</span><span class="sxs-lookup"><span data-stu-id="90cbf-121">Requirements</span></span>  
 <span data-ttu-id="90cbf-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90cbf-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90cbf-123">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="90cbf-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90cbf-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="90cbf-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90cbf-125">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90cbf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90cbf-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90cbf-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="90cbf-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="90cbf-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="90cbf-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="90cbf-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
