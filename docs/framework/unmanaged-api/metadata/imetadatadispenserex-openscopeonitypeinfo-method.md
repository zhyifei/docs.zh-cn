---
title: IMetaDataDispenserEx::OpenScopeOnITypeInfo 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5fd96f390b0bba60d1b95d20273bbf670208d41
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456527"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="bb470-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="bb470-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="bb470-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="bb470-103">This method is not implemented.</span></span> <span data-ttu-id="bb470-104">如果调用，则返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="bb470-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb470-105">语法</span><span class="sxs-lookup"><span data-stu-id="bb470-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb470-106">参数</span><span class="sxs-lookup"><span data-stu-id="bb470-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="bb470-107">[in]指向[ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo)接口，用于提供在其上打开作用域的类型信息。</span><span class="sxs-lookup"><span data-stu-id="bb470-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="bb470-108">[in]打开模式的标志。</span><span class="sxs-lookup"><span data-stu-id="bb470-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="bb470-109">[in]所需的接口。</span><span class="sxs-lookup"><span data-stu-id="bb470-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="bb470-110">[out]指针到指向返回的接口。</span><span class="sxs-lookup"><span data-stu-id="bb470-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb470-111">要求</span><span class="sxs-lookup"><span data-stu-id="bb470-111">Requirements</span></span>  
 <span data-ttu-id="bb470-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb470-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb470-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb470-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb470-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bb470-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb470-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb470-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb470-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb470-116">See Also</span></span>  
 [<span data-ttu-id="bb470-117">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="bb470-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="bb470-118">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="bb470-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
