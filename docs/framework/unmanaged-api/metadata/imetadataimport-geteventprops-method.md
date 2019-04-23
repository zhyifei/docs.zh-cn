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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 138be940c6a03fc58e488e344455946bdb832bab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214515"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="67384-102">IMetaDataImport::GetEventProps 方法</span><span class="sxs-lookup"><span data-stu-id="67384-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="67384-103">获取由指定的事件标记，包括声明类型、 添加和删除方法的委托，任何标志及其他关联的数据所表示的事件的元数据信息。</span><span class="sxs-lookup"><span data-stu-id="67384-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67384-104">语法</span><span class="sxs-lookup"><span data-stu-id="67384-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="67384-105">参数</span><span class="sxs-lookup"><span data-stu-id="67384-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="67384-106">[in]表示要获取的元数据的事件的事件元数据标记。</span><span class="sxs-lookup"><span data-stu-id="67384-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="67384-107">[out]指向表示声明事件的类的 TypeDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="67384-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="67384-108">[out]引用的事件名称`ev`。</span><span class="sxs-lookup"><span data-stu-id="67384-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="67384-109">[in]请求的长度以宽字符为单位`szEvent`。</span><span class="sxs-lookup"><span data-stu-id="67384-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="67384-110">[out]中的宽字符返回的长度`szEvent`。</span><span class="sxs-lookup"><span data-stu-id="67384-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="67384-111">[out]一个指向 TypeRef 或 TypeDef 元数据令牌表示<xref:System.Delegate>事件的类型。</span><span class="sxs-lookup"><span data-stu-id="67384-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="67384-112">[out]指向表示为事件添加处理程序的方法的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="67384-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="67384-113">[out]指向表示移除事件处理程序的方法的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="67384-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="67384-114">[out]指向表示引发事件的方法的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="67384-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="67384-115">[out]与其他方法与事件关联的令牌指针的数组。</span><span class="sxs-lookup"><span data-stu-id="67384-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="67384-116">[in] `rmdOtherMethod` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="67384-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="67384-117">[out]在返回的标记数`rmdOtherMethod`。</span><span class="sxs-lookup"><span data-stu-id="67384-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67384-118">要求</span><span class="sxs-lookup"><span data-stu-id="67384-118">Requirements</span></span>  
 <span data-ttu-id="67384-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67384-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67384-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67384-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67384-121">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="67384-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67384-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67384-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67384-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="67384-123">See also</span></span>

- [<span data-ttu-id="67384-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="67384-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="67384-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="67384-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
