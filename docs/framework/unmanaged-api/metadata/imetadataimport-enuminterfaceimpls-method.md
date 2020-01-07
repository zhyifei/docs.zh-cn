---
title: IMetaDataImport::EnumInterfaceImpls 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338055"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="60829-102">IMetaDataImport::EnumInterfaceImpls 方法</span><span class="sxs-lookup"><span data-stu-id="60829-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="60829-103">枚举由指定 `TypeDef`实现的所有接口。</span><span class="sxs-lookup"><span data-stu-id="60829-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="60829-104">语法</span><span class="sxs-lookup"><span data-stu-id="60829-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60829-105">参数</span><span class="sxs-lookup"><span data-stu-id="60829-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="60829-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="60829-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="60829-107">中要枚举其 MethodDef 标记表示接口实现的 TypeDef 的标记。</span><span class="sxs-lookup"><span data-stu-id="60829-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="60829-108">弄用于存储 MethodDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="60829-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="60829-109">中`rImpls` 数组的最大长度。</span><span class="sxs-lookup"><span data-stu-id="60829-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="60829-110">弄`rImpls`中返回的标记的实际数量。</span><span class="sxs-lookup"><span data-stu-id="60829-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60829-111">返回值</span><span class="sxs-lookup"><span data-stu-id="60829-111">Return Value</span></span>  
  
|<span data-ttu-id="60829-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60829-112">HRESULT</span></span>|<span data-ttu-id="60829-113">描述</span><span class="sxs-lookup"><span data-stu-id="60829-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="60829-114">`EnumInterfaceImpls` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="60829-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="60829-115">没有要枚举的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="60829-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="60829-116">在这种情况下，`pcImpls` 设置为零。</span><span class="sxs-lookup"><span data-stu-id="60829-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="60829-117">备注</span><span class="sxs-lookup"><span data-stu-id="60829-117">Remarks</span></span>

<span data-ttu-id="60829-118">枚举为指定的 `TypeDef`实现的每个接口返回 `mdInterfaceImpl` 标记的集合。</span><span class="sxs-lookup"><span data-stu-id="60829-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="60829-119">接口令牌按指定的顺序（通过 `DefineTypeDef` 或 `SetTypeDefProps`）返回。</span><span class="sxs-lookup"><span data-stu-id="60829-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="60829-120">可以使用[GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)查询返回 `mdInterfaceImpl` 标记的属性。</span><span class="sxs-lookup"><span data-stu-id="60829-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="60829-121">需求</span><span class="sxs-lookup"><span data-stu-id="60829-121">Requirements</span></span>  
 <span data-ttu-id="60829-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="60829-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60829-123">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="60829-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60829-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="60829-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60829-125">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60829-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60829-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60829-126">See also</span></span>

- [<span data-ttu-id="60829-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="60829-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="60829-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="60829-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
