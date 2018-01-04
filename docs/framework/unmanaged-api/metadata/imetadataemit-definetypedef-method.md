---
title: "IMetaDataEmit::DefineTypeDef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeDef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da8fed37605252139428aa40bb3785c242d95cac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="290a3-102">IMetaDataEmit::DefineTypeDef 方法</span><span class="sxs-lookup"><span data-stu-id="290a3-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="290a3-103">创建一个类型定义的公共语言运行时类型，并获取该类型定义元数据标记。</span><span class="sxs-lookup"><span data-stu-id="290a3-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="290a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="290a3-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="290a3-105">参数</span><span class="sxs-lookup"><span data-stu-id="290a3-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="290a3-106">[in]以 Unicode 类型的名称。</span><span class="sxs-lookup"><span data-stu-id="290a3-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="290a3-107">[in]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="290a3-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="290a3-108">这是一个位掩码的`CoreTypeAttr`值。</span><span class="sxs-lookup"><span data-stu-id="290a3-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="290a3-109">[in]基本类的标记。</span><span class="sxs-lookup"><span data-stu-id="290a3-109">[in] The token of the base class.</span></span> <span data-ttu-id="290a3-110">它必须是`mdTypeDef`或`mdTypeRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="290a3-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="290a3-111">[in]指定此类或接口实现的接口的令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="290a3-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="290a3-112">[out]`mdTypeDef`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="290a3-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="290a3-113">备注</span><span class="sxs-lookup"><span data-stu-id="290a3-113">Remarks</span></span>  
 <span data-ttu-id="290a3-114">一个标志`dwTypeDefFlags`指定正在创建的类型是通用类型系统引用类型 （类或接口） 还是通用类型系统值类型。</span><span class="sxs-lookup"><span data-stu-id="290a3-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="290a3-115">根据提供的参数，此方法的副作用，还可以创建`mdInterfaceImpl`记录为每个接口继承或实现是用这种类型。</span><span class="sxs-lookup"><span data-stu-id="290a3-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="290a3-116">但是，，此方法不返回任何这些`mdInterfaceImpl`令牌。</span><span class="sxs-lookup"><span data-stu-id="290a3-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="290a3-117">如果客户端想要以后添加或修改`mdInterfaceImpl`令牌，它必须使用`IMetaDataImport`接口来枚举它们。</span><span class="sxs-lookup"><span data-stu-id="290a3-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="290a3-118">如果你想要使用的 COM 语义`[default]`接口，还应为中的第一个元素提供的默认接口`rtkImplements`; 在类上设置的自定义特性将指示此类具有的默认接口 (其始终被假定为第一次`mdInterfaceImpl`类声明的令牌)。</span><span class="sxs-lookup"><span data-stu-id="290a3-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="290a3-119">每个元素`rtkImplements`数组`mdTypeDef`或`mdTypeRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="290a3-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="290a3-120">数组中的最后一个元素必须是`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="290a3-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="290a3-121">惠?</span><span class="sxs-lookup"><span data-stu-id="290a3-121">Requirements</span></span>  
 <span data-ttu-id="290a3-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="290a3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="290a3-123">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="290a3-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="290a3-124">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="290a3-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="290a3-125">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="290a3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290a3-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="290a3-126">See Also</span></span>  
 [<span data-ttu-id="290a3-127">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="290a3-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="290a3-128">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="290a3-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
