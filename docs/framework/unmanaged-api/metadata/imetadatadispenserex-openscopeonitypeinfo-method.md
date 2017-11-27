---
title: "IMetaDataDispenserEx::OpenScopeOnITypeInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a0838895870370e3003aac4967a535b44c8e7943
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="9d4e3-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="9d4e3-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="9d4e3-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="9d4e3-103">This method is not implemented.</span></span> <span data-ttu-id="9d4e3-104">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="9d4e3-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4e3-105">语法</span><span class="sxs-lookup"><span data-stu-id="9d4e3-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d4e3-106">参数</span><span class="sxs-lookup"><span data-stu-id="9d4e3-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="9d4e3-107">[in]指向[ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680)提供在其上打开作用域的类型信息的接口。</span><span class="sxs-lookup"><span data-stu-id="9d4e3-107">[in] Pointer to an [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="9d4e3-108">[in]打开模式的标志。</span><span class="sxs-lookup"><span data-stu-id="9d4e3-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="9d4e3-109">[in]所需的接口。</span><span class="sxs-lookup"><span data-stu-id="9d4e3-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="9d4e3-110">[out]指向返回的接口指针。</span><span class="sxs-lookup"><span data-stu-id="9d4e3-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d4e3-111">要求</span><span class="sxs-lookup"><span data-stu-id="9d4e3-111">Requirements</span></span>  
 <span data-ttu-id="9d4e3-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d4e3-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d4e3-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d4e3-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d4e3-114">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9d4e3-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d4e3-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d4e3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4e3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d4e3-116">See Also</span></span>  
 [<span data-ttu-id="9d4e3-117">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="9d4e3-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="9d4e3-118">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="9d4e3-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
