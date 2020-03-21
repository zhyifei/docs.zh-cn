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
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175377"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="f01a4-102">IMetaDataImport::GetInterfaceImplProps 方法</span><span class="sxs-lookup"><span data-stu-id="f01a4-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="f01a4-103">获取实现指定方法的 的 元数据<xref:System.Type>令牌以及声明该方法的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="f01a4-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f01a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="f01a4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f01a4-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f01a4-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="f01a4-106">[在]表示要返回类和接口令牌的方法的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="f01a4-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="f01a4-107">[出]表示实现方法的类的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="f01a4-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="f01a4-108">[出]表示定义已实现方法的接口的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="f01a4-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="f01a4-109">备注</span><span class="sxs-lookup"><span data-stu-id="f01a4-109">Remarks</span></span>

 <span data-ttu-id="f01a4-110">通过调用`iImpl`[EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md)方法，可以获取 的值。</span><span class="sxs-lookup"><span data-stu-id="f01a4-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="f01a4-111">例如，假设一个类的`mdTypeDef`令牌值为 0x02000007，并且它实现了三个接口，其类型具有令牌：</span><span class="sxs-lookup"><span data-stu-id="f01a4-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="f01a4-112">0x0200003 （类型定义）</span><span class="sxs-lookup"><span data-stu-id="f01a4-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="f01a4-113">0x0100000A （类型参考）</span><span class="sxs-lookup"><span data-stu-id="f01a4-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="f01a4-114">0x0200001C （类型定义）</span><span class="sxs-lookup"><span data-stu-id="f01a4-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="f01a4-115">从概念上讲，此信息存储在接口实现表中，如：</span><span class="sxs-lookup"><span data-stu-id="f01a4-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="f01a4-116">行号</span><span class="sxs-lookup"><span data-stu-id="f01a4-116">Row number</span></span> | <span data-ttu-id="f01a4-117">类令牌</span><span class="sxs-lookup"><span data-stu-id="f01a4-117">Class token</span></span> | <span data-ttu-id="f01a4-118">接口令牌</span><span class="sxs-lookup"><span data-stu-id="f01a4-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="f01a4-119">4</span><span class="sxs-lookup"><span data-stu-id="f01a4-119">4</span></span>          |             |                 |
| <span data-ttu-id="f01a4-120">5</span><span class="sxs-lookup"><span data-stu-id="f01a4-120">5</span></span>          | <span data-ttu-id="f01a4-121">02000007</span><span class="sxs-lookup"><span data-stu-id="f01a4-121">02000007</span></span>    | <span data-ttu-id="f01a4-122">02000003</span><span class="sxs-lookup"><span data-stu-id="f01a4-122">02000003</span></span>        |
| <span data-ttu-id="f01a4-123">6</span><span class="sxs-lookup"><span data-stu-id="f01a4-123">6</span></span>          | <span data-ttu-id="f01a4-124">02000007</span><span class="sxs-lookup"><span data-stu-id="f01a4-124">02000007</span></span>    | <span data-ttu-id="f01a4-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="f01a4-125">0100000A</span></span>        |
| <span data-ttu-id="f01a4-126">7</span><span class="sxs-lookup"><span data-stu-id="f01a4-126">7</span></span>          |             |                 |
| <span data-ttu-id="f01a4-127">8</span><span class="sxs-lookup"><span data-stu-id="f01a4-127">8</span></span>          | <span data-ttu-id="f01a4-128">02000007</span><span class="sxs-lookup"><span data-stu-id="f01a4-128">02000007</span></span>    | <span data-ttu-id="f01a4-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="f01a4-129">0200001C</span></span>        |

<span data-ttu-id="f01a4-130">回想，令牌是 4 字节的值：</span><span class="sxs-lookup"><span data-stu-id="f01a4-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="f01a4-131">较低的 3 个字节保留行号或 RID。</span><span class="sxs-lookup"><span data-stu-id="f01a4-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="f01a4-132">上字节保存的令牌类型 = 0x09。 `mdtInterfaceImpl`</span><span class="sxs-lookup"><span data-stu-id="f01a4-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="f01a4-133">`GetInterfaceImplProps`返回您在`iImpl`参数中提供的令牌行中持有的信息。</span><span class="sxs-lookup"><span data-stu-id="f01a4-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f01a4-134">要求</span><span class="sxs-lookup"><span data-stu-id="f01a4-134">Requirements</span></span>  
 <span data-ttu-id="f01a4-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f01a4-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f01a4-136">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="f01a4-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f01a4-137">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="f01a4-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f01a4-138">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f01a4-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f01a4-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f01a4-139">See also</span></span>

- [<span data-ttu-id="f01a4-140">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f01a4-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f01a4-141">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f01a4-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
