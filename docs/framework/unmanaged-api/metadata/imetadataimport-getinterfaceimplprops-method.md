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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115929"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="58c29-102">IMetaDataImport::GetInterfaceImplProps 方法</span><span class="sxs-lookup"><span data-stu-id="58c29-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="58c29-103">获取一个指针指向的元数据令牌<xref:System.Type>实现指定的方法和接口，其用于声明该方法。</span><span class="sxs-lookup"><span data-stu-id="58c29-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="58c29-104">语法</span><span class="sxs-lookup"><span data-stu-id="58c29-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58c29-105">参数</span><span class="sxs-lookup"><span data-stu-id="58c29-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="58c29-106">[in]表示此方法返回的类和接口令牌的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="58c29-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="58c29-107">[out]表示实现方法的类的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="58c29-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="58c29-108">[out]表示定义实现的方法的接口的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="58c29-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="58c29-109">备注</span><span class="sxs-lookup"><span data-stu-id="58c29-109">Remarks</span></span>

 <span data-ttu-id="58c29-110">获取值以供`iImpl`通过调用[EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="58c29-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="58c29-111">例如，假设类具有`mdTypeDef`令牌 0x02000007 的值，它实现的类型具有令牌的三个接口：</span><span class="sxs-lookup"><span data-stu-id="58c29-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="58c29-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="58c29-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="58c29-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="58c29-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="58c29-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="58c29-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="58c29-115">从概念上讲，此信息存储到作为接口实现表：</span><span class="sxs-lookup"><span data-stu-id="58c29-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="58c29-116">行号</span><span class="sxs-lookup"><span data-stu-id="58c29-116">Row number</span></span> | <span data-ttu-id="58c29-117">类令牌</span><span class="sxs-lookup"><span data-stu-id="58c29-117">Class token</span></span> | <span data-ttu-id="58c29-118">接口令牌</span><span class="sxs-lookup"><span data-stu-id="58c29-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="58c29-119">4</span><span class="sxs-lookup"><span data-stu-id="58c29-119">4</span></span>          |             |                 |
| <span data-ttu-id="58c29-120">5</span><span class="sxs-lookup"><span data-stu-id="58c29-120">5</span></span>          | <span data-ttu-id="58c29-121">02000007</span><span class="sxs-lookup"><span data-stu-id="58c29-121">02000007</span></span>    | <span data-ttu-id="58c29-122">02000003</span><span class="sxs-lookup"><span data-stu-id="58c29-122">02000003</span></span>        |
| <span data-ttu-id="58c29-123">6</span><span class="sxs-lookup"><span data-stu-id="58c29-123">6</span></span>          | <span data-ttu-id="58c29-124">02000007</span><span class="sxs-lookup"><span data-stu-id="58c29-124">02000007</span></span>    | <span data-ttu-id="58c29-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="58c29-125">0100000A</span></span>        |
| <span data-ttu-id="58c29-126">7</span><span class="sxs-lookup"><span data-stu-id="58c29-126">7</span></span>          |             |                 |
| <span data-ttu-id="58c29-127">8</span><span class="sxs-lookup"><span data-stu-id="58c29-127">8</span></span>          | <span data-ttu-id="58c29-128">02000007</span><span class="sxs-lookup"><span data-stu-id="58c29-128">02000007</span></span>    | <span data-ttu-id="58c29-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="58c29-129">0200001C</span></span>        |

<span data-ttu-id="58c29-130">请注意，该令牌是一个 4 字节值：</span><span class="sxs-lookup"><span data-stu-id="58c29-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="58c29-131">较低的 3 个字节存储的行号，或 RID。</span><span class="sxs-lookup"><span data-stu-id="58c29-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="58c29-132">高位字节包含标记类型 – 为 0x09 `mdtInterfaceImpl`。</span><span class="sxs-lookup"><span data-stu-id="58c29-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="58c29-133">`GetInterfaceImplProps` 返回信息保存在行中提供的令牌`iImpl`参数。</span><span class="sxs-lookup"><span data-stu-id="58c29-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="58c29-134">要求</span><span class="sxs-lookup"><span data-stu-id="58c29-134">Requirements</span></span>  
 <span data-ttu-id="58c29-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58c29-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c29-136">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="58c29-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58c29-137">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="58c29-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58c29-138">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c29-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c29-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="58c29-139">See also</span></span>

- [<span data-ttu-id="58c29-140">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="58c29-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="58c29-141">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="58c29-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
