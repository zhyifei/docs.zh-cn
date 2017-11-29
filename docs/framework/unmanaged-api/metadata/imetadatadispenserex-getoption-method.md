---
title: "IMetaDataDispenserEx::GetOption 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fa9db222c81c2d6536b782c3e047e24c773bd018
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="34d26-102">IMetaDataDispenserEx::GetOption 方法</span><span class="sxs-lookup"><span data-stu-id="34d26-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="34d26-103">获取当前元数据范围的指定选项的值。</span><span class="sxs-lookup"><span data-stu-id="34d26-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="34d26-104">选项控制如何处理对当前的元数据范围的调用。</span><span class="sxs-lookup"><span data-stu-id="34d26-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34d26-105">语法</span><span class="sxs-lookup"><span data-stu-id="34d26-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34d26-106">参数</span><span class="sxs-lookup"><span data-stu-id="34d26-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="34d26-107">[in]指向指定要检索的选项的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="34d26-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="34d26-108">请参阅受支持的 Guid 列表的备注部分。</span><span class="sxs-lookup"><span data-stu-id="34d26-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="34d26-109">[out]返回选项的值。</span><span class="sxs-lookup"><span data-stu-id="34d26-109">[out] The value of the returned option.</span></span> <span data-ttu-id="34d26-110">此值的类型将是类型的指定的选项的变体。</span><span class="sxs-lookup"><span data-stu-id="34d26-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34d26-111">备注</span><span class="sxs-lookup"><span data-stu-id="34d26-111">Remarks</span></span>  
 <span data-ttu-id="34d26-112">以下列表显示为此方法支持的 Guid。</span><span class="sxs-lookup"><span data-stu-id="34d26-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="34d26-113">有关说明，请参阅[imetadatadispenserex:: Setoption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="34d26-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="34d26-114">如果`optionId`是不在此列表中，此方法返回的 HRESULT `E_INVALIDARG`，指示不正确的参数。</span><span class="sxs-lookup"><span data-stu-id="34d26-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="34d26-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="34d26-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="34d26-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="34d26-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="34d26-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="34d26-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="34d26-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="34d26-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="34d26-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="34d26-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="34d26-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="34d26-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="34d26-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="34d26-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34d26-122">要求</span><span class="sxs-lookup"><span data-stu-id="34d26-122">Requirements</span></span>  
 <span data-ttu-id="34d26-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34d26-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34d26-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34d26-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34d26-125">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="34d26-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34d26-126">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34d26-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d26-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34d26-127">See Also</span></span>  
 [<span data-ttu-id="34d26-128">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="34d26-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="34d26-129">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="34d26-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
