---
title: IMetaDataImport::EnumMethodSemantics 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: ff6932b6040a19e0ccda2f8d2140fa131cdd9224
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450075"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="62797-102">IMetaDataImport::EnumMethodSemantics 方法</span><span class="sxs-lookup"><span data-stu-id="62797-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="62797-103">枚举与指定方法相关的属性和属性更改事件。</span><span class="sxs-lookup"><span data-stu-id="62797-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62797-104">语法</span><span class="sxs-lookup"><span data-stu-id="62797-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62797-105">参数</span><span class="sxs-lookup"><span data-stu-id="62797-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="62797-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="62797-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="62797-107">第一次调用此方法时，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="62797-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="62797-108">中用于限制枚举范围的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="62797-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="62797-109">弄用于存储事件或属性的数组。</span><span class="sxs-lookup"><span data-stu-id="62797-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="62797-110">[in] `rEventProp` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="62797-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="62797-111">弄`rEventProp`中返回的事件或属性的数目。</span><span class="sxs-lookup"><span data-stu-id="62797-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62797-112">返回值</span><span class="sxs-lookup"><span data-stu-id="62797-112">Return Value</span></span>  
  
|<span data-ttu-id="62797-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62797-113">HRESULT</span></span>|<span data-ttu-id="62797-114">说明</span><span class="sxs-lookup"><span data-stu-id="62797-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="62797-115">`EnumMethodSemantics` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="62797-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="62797-116">没有要枚举的事件或属性。</span><span class="sxs-lookup"><span data-stu-id="62797-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="62797-117">在这种情况下，`pcEventProp` 为零。</span><span class="sxs-lookup"><span data-stu-id="62797-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62797-118">备注</span><span class="sxs-lookup"><span data-stu-id="62797-118">Remarks</span></span>  
 <span data-ttu-id="62797-119">许多公共语言运行时类型都定义*属性*`Changed` 事件和 `On`*属性*`Changed` 与它们属性相关的方法。</span><span class="sxs-lookup"><span data-stu-id="62797-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="62797-120">例如，<xref:System.Windows.Forms.Control?displayProperty=nameWithType> 类型定义了 <xref:System.Windows.Forms.Control.Font%2A> 属性、<xref:System.Windows.Forms.Control.FontChanged> 事件和 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="62797-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="62797-121"><xref:System.Windows.Forms.Control.Font%2A> 属性的 set 访问器方法将调用 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 方法，进而引发 <xref:System.Windows.Forms.Control.FontChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="62797-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="62797-122">你将使用 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 的 MethodDef 调用 `EnumMethodSemantics`，以获取对 <xref:System.Windows.Forms.Control.Font%2A> 属性和 <xref:System.Windows.Forms.Control.FontChanged> 事件的引用。</span><span class="sxs-lookup"><span data-stu-id="62797-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62797-123">要求</span><span class="sxs-lookup"><span data-stu-id="62797-123">Requirements</span></span>  
 <span data-ttu-id="62797-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62797-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62797-125">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="62797-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62797-126">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="62797-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62797-127">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62797-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62797-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62797-128">See also</span></span>

- [<span data-ttu-id="62797-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="62797-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="62797-130">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="62797-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
