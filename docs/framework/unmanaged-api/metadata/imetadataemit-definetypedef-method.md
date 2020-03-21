---
title: IMetaDataEmit::DefineTypeDef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175754"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="a0a13-102">IMetaDataEmit::DefineTypeDef 方法</span><span class="sxs-lookup"><span data-stu-id="a0a13-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="a0a13-103">为通用语言运行时类型创建类型定义，并获取该类型定义的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="a0a13-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a13-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0a13-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0a13-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a0a13-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="a0a13-106">[在]Unicode 中类型的名称。</span><span class="sxs-lookup"><span data-stu-id="a0a13-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="a0a13-107">[在]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="a0a13-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="a0a13-108">这是值的`CoreTypeAttr`位掩码。</span><span class="sxs-lookup"><span data-stu-id="a0a13-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="a0a13-109">[在]基类的令牌。</span><span class="sxs-lookup"><span data-stu-id="a0a13-109">[in] The token of the base class.</span></span> <span data-ttu-id="a0a13-110">它必须是 或`mdTypeDef``mdTypeRef`标记。</span><span class="sxs-lookup"><span data-stu-id="a0a13-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="a0a13-111">[在]指定此类或接口实现的接口的令牌数组。</span><span class="sxs-lookup"><span data-stu-id="a0a13-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="a0a13-112">[出]分配的`mdTypeDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="a0a13-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0a13-113">备注</span><span class="sxs-lookup"><span data-stu-id="a0a13-113">Remarks</span></span>  
 <span data-ttu-id="a0a13-114">中`dwTypeDefFlags`的标志指定正在创建的类型是公共类型系统引用类型（类或接口）还是公共类型系统值类型。</span><span class="sxs-lookup"><span data-stu-id="a0a13-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="a0a13-115">根据提供的参数，此方法作为副作用，还可以为此类型继承或实现的每个接口创建`mdInterfaceImpl`记录。</span><span class="sxs-lookup"><span data-stu-id="a0a13-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="a0a13-116">但是，此方法不会返回任何这些`mdInterfaceImpl`令牌。</span><span class="sxs-lookup"><span data-stu-id="a0a13-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="a0a13-117">如果客户端希望以后添加或修改`mdInterfaceImpl`令牌，则必须使用接口`IMetaDataImport`枚举它们。</span><span class="sxs-lookup"><span data-stu-id="a0a13-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="a0a13-118">如果要使用接口的`[default]`COM 语义，则应将默认接口作为`rtkImplements`中的第一个元素提供 。类上的自定义属性集将指示类具有默认接口（始终假定该接口是为类声明的第一个`mdInterfaceImpl`令牌）。</span><span class="sxs-lookup"><span data-stu-id="a0a13-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="a0a13-119">`rtkImplements`数组的每个元素都包含 或`mdTypeDef``mdTypeRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="a0a13-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="a0a13-120">数组中的最后一个元素必须为`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="a0a13-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a13-121">要求</span><span class="sxs-lookup"><span data-stu-id="a0a13-121">Requirements</span></span>  
 <span data-ttu-id="a0a13-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0a13-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0a13-123">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a0a13-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0a13-124">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a0a13-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0a13-125">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a13-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a13-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0a13-126">See also</span></span>

- [<span data-ttu-id="a0a13-127">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="a0a13-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a0a13-128">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="a0a13-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
