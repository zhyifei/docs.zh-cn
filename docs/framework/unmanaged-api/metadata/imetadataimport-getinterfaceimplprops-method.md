---
title: IMetaDataImport::GetInterfaceImplProps 方法
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e2ebbd47a5e36a722fce33ba67d7efb4db8675
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777762"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="5d42e-102">IMetaDataImport::GetInterfaceImplProps 方法</span><span class="sxs-lookup"><span data-stu-id="5d42e-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="5d42e-103">获取一个指针指向的元数据令牌<xref:System.Type>实现指定的方法和接口，其用于声明该方法。</span><span class="sxs-lookup"><span data-stu-id="5d42e-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5d42e-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d42e-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d42e-105">参数</span><span class="sxs-lookup"><span data-stu-id="5d42e-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="5d42e-106">[in]表示此方法返回的类和接口令牌的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5d42e-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="5d42e-107">[out]表示实现方法的类的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5d42e-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="5d42e-108">[out]表示定义实现的方法的接口的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5d42e-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="5d42e-109">备注</span><span class="sxs-lookup"><span data-stu-id="5d42e-109">Remarks</span></span>

 <span data-ttu-id="5d42e-110">获取值以供`iImpl`通过调用[EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5d42e-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="5d42e-111">例如，假设类具有`mdTypeDef`令牌 0x02000007 的值，它实现的类型具有令牌的三个接口：</span><span class="sxs-lookup"><span data-stu-id="5d42e-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="5d42e-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="5d42e-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="5d42e-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="5d42e-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="5d42e-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="5d42e-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="5d42e-115">从概念上讲，此信息存储到作为接口实现表：</span><span class="sxs-lookup"><span data-stu-id="5d42e-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="5d42e-116">行号</span><span class="sxs-lookup"><span data-stu-id="5d42e-116">Row number</span></span> | <span data-ttu-id="5d42e-117">类令牌</span><span class="sxs-lookup"><span data-stu-id="5d42e-117">Class token</span></span> | <span data-ttu-id="5d42e-118">接口令牌</span><span class="sxs-lookup"><span data-stu-id="5d42e-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="5d42e-119">4</span><span class="sxs-lookup"><span data-stu-id="5d42e-119">4</span></span>          |             |                 |
| <span data-ttu-id="5d42e-120">5</span><span class="sxs-lookup"><span data-stu-id="5d42e-120">5</span></span>          | <span data-ttu-id="5d42e-121">02000007</span><span class="sxs-lookup"><span data-stu-id="5d42e-121">02000007</span></span>    | <span data-ttu-id="5d42e-122">02000003</span><span class="sxs-lookup"><span data-stu-id="5d42e-122">02000003</span></span>        |
| <span data-ttu-id="5d42e-123">6</span><span class="sxs-lookup"><span data-stu-id="5d42e-123">6</span></span>          | <span data-ttu-id="5d42e-124">02000007</span><span class="sxs-lookup"><span data-stu-id="5d42e-124">02000007</span></span>    | <span data-ttu-id="5d42e-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="5d42e-125">0100000A</span></span>        |
| <span data-ttu-id="5d42e-126">7</span><span class="sxs-lookup"><span data-stu-id="5d42e-126">7</span></span>          |             |                 |
| <span data-ttu-id="5d42e-127">8</span><span class="sxs-lookup"><span data-stu-id="5d42e-127">8</span></span>          | <span data-ttu-id="5d42e-128">02000007</span><span class="sxs-lookup"><span data-stu-id="5d42e-128">02000007</span></span>    | <span data-ttu-id="5d42e-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="5d42e-129">0200001C</span></span>        |

<span data-ttu-id="5d42e-130">请注意，该令牌是一个 4 字节值：</span><span class="sxs-lookup"><span data-stu-id="5d42e-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="5d42e-131">较低的 3 个字节存储的行号，或 RID。</span><span class="sxs-lookup"><span data-stu-id="5d42e-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="5d42e-132">高位字节包含标记类型 – 为 0x09 `mdtInterfaceImpl`。</span><span class="sxs-lookup"><span data-stu-id="5d42e-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="5d42e-133">`GetInterfaceImplProps` 返回信息保存在行中提供的令牌`iImpl`参数。</span><span class="sxs-lookup"><span data-stu-id="5d42e-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="5d42e-134">要求</span><span class="sxs-lookup"><span data-stu-id="5d42e-134">Requirements</span></span>  
 <span data-ttu-id="5d42e-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d42e-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d42e-136">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d42e-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d42e-137">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5d42e-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d42e-138">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d42e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d42e-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d42e-139">See also</span></span>

- [<span data-ttu-id="5d42e-140">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="5d42e-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5d42e-141">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="5d42e-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
