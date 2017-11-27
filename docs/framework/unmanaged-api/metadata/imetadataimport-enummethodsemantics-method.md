---
title: "IMetaDataImport::EnumMethodSemantics 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d5ec79701f73b8beb7759d72b972fc347a339c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="78cf0-102">IMetaDataImport::EnumMethodSemantics 方法</span><span class="sxs-lookup"><span data-stu-id="78cf0-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="78cf0-103">枚举与指定方法相关的属性和属性更改事件。</span><span class="sxs-lookup"><span data-stu-id="78cf0-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78cf0-104">语法</span><span class="sxs-lookup"><span data-stu-id="78cf0-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78cf0-105">参数</span><span class="sxs-lookup"><span data-stu-id="78cf0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="78cf0-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="78cf0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="78cf0-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="78cf0-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="78cf0-108">[in]限制在枚举的作用域的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="78cf0-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="78cf0-109">[out]用于存储事件或属性的数组。</span><span class="sxs-lookup"><span data-stu-id="78cf0-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="78cf0-110">[in] `rEventProp` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="78cf0-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="78cf0-111">[out]事件或属性中返回的数`rEventProp`。</span><span class="sxs-lookup"><span data-stu-id="78cf0-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78cf0-112">返回值</span><span class="sxs-lookup"><span data-stu-id="78cf0-112">Return Value</span></span>  
  
|<span data-ttu-id="78cf0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78cf0-113">HRESULT</span></span>|<span data-ttu-id="78cf0-114">描述</span><span class="sxs-lookup"><span data-stu-id="78cf0-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="78cf0-115">`EnumMethodSemantics`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="78cf0-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="78cf0-116">没有任何事件或属性，以枚举。</span><span class="sxs-lookup"><span data-stu-id="78cf0-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="78cf0-117">在这种情况下，`pcEventProp`为零。</span><span class="sxs-lookup"><span data-stu-id="78cf0-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78cf0-118">备注</span><span class="sxs-lookup"><span data-stu-id="78cf0-118">Remarks</span></span>  
 <span data-ttu-id="78cf0-119">许多公共语言运行时类型定义*属性*`Changed`事件和`On`*属性*`Changed`其属性与相关方法。</span><span class="sxs-lookup"><span data-stu-id="78cf0-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="78cf0-120">例如，<xref:System.Windows.Forms.Control?displayProperty=nameWithType>类型定义<xref:System.Windows.Forms.Control.Font%2A>属性，<xref:System.Windows.Forms.Control.FontChanged>事件，和<xref:System.Windows.Forms.Control.OnFontChanged%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="78cf0-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="78cf0-121">Set 访问器方法的<xref:System.Windows.Forms.Control.Font%2A>属性调用<xref:System.Windows.Forms.Control.OnFontChanged%2A>方法，该方法引发<xref:System.Windows.Forms.Control.FontChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="78cf0-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="78cf0-122">你应该调用`EnumMethodSemantics`使用为 MethodDef<xref:System.Windows.Forms.Control.OnFontChanged%2A>若要获取对引用<xref:System.Windows.Forms.Control.Font%2A>属性和<xref:System.Windows.Forms.Control.FontChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="78cf0-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78cf0-123">要求</span><span class="sxs-lookup"><span data-stu-id="78cf0-123">Requirements</span></span>  
 <span data-ttu-id="78cf0-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78cf0-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78cf0-125">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="78cf0-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78cf0-126">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="78cf0-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78cf0-127">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78cf0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78cf0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78cf0-128">See Also</span></span>  
 [<span data-ttu-id="78cf0-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="78cf0-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="78cf0-130">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="78cf0-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
