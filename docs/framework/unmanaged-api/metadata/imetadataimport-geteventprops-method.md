---
title: IMetaDataImport::GetEventProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177268"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="267d3-102">IMetaDataImport::GetEventProps 方法</span><span class="sxs-lookup"><span data-stu-id="267d3-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="267d3-103">获取由指定事件令牌表示的事件的元数据信息，包括声明类型、代理的添加和删除方法以及任何标志和其他关联数据。</span><span class="sxs-lookup"><span data-stu-id="267d3-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="267d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,
   [out] LPCWSTR       szEvent,
   [in]  ULONG         cchEvent,
   [out] ULONG         *pchEvent,
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,
   [out] mdMethodDef   *pmdRemoveOn,
   [out] mdMethodDef   *pmdFire,
   [out] mdMethodDef   rmdOtherMethod[],
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="267d3-105">parameters</span><span class="sxs-lookup"><span data-stu-id="267d3-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="267d3-106">[在]表示要获取其元数据的事件元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="267d3-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="267d3-107">[出]指向表示声明事件的类的 TypeDef 令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="267d3-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="267d3-108">[出]引用`ev`的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="267d3-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="267d3-109">[在]请求的长度以宽字符。 `szEvent`</span><span class="sxs-lookup"><span data-stu-id="267d3-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="267d3-110">[出]返回的长度以宽字符。 `szEvent`</span><span class="sxs-lookup"><span data-stu-id="267d3-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="267d3-111">[出]指向表示事件<xref:System.Delegate>类型的 TypeRef 或 TypeDef 元数据令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="267d3-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="267d3-112">[出]指向元数据令牌的指针，表示为事件添加处理程序的方法。</span><span class="sxs-lookup"><span data-stu-id="267d3-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="267d3-113">[出]指向表示删除事件处理程序的方法的元数据令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="267d3-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="267d3-114">[出]指向表示引发事件的方法的元数据令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="267d3-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="267d3-115">[出]指向与事件关联的其他方法的令牌指针数组。</span><span class="sxs-lookup"><span data-stu-id="267d3-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="267d3-116">[in] `rmdOtherMethod` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="267d3-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="267d3-117">[出]在 中`rmdOtherMethod`返回的令牌数。</span><span class="sxs-lookup"><span data-stu-id="267d3-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="267d3-118">要求</span><span class="sxs-lookup"><span data-stu-id="267d3-118">Requirements</span></span>  
 <span data-ttu-id="267d3-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="267d3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="267d3-120">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="267d3-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="267d3-121">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="267d3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="267d3-122">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="267d3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267d3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="267d3-123">See also</span></span>

- [<span data-ttu-id="267d3-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="267d3-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="267d3-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="267d3-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
