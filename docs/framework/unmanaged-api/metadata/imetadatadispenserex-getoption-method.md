---
title: IMetaDataDispenserEx::GetOption 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6287b7adf0ef6f6269a51f608657444f5fa7f74e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580221"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="676d0-102">IMetaDataDispenserEx::GetOption 方法</span><span class="sxs-lookup"><span data-stu-id="676d0-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="676d0-103">获取当前元数据范围的指定选项的值。</span><span class="sxs-lookup"><span data-stu-id="676d0-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="676d0-104">选项，可以控制如何处理对当前元数据范围的调用。</span><span class="sxs-lookup"><span data-stu-id="676d0-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="676d0-105">语法</span><span class="sxs-lookup"><span data-stu-id="676d0-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="676d0-106">参数</span><span class="sxs-lookup"><span data-stu-id="676d0-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="676d0-107">[in]一个指向指定要检索的选项的 GUID。</span><span class="sxs-lookup"><span data-stu-id="676d0-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="676d0-108">请参阅受支持的 Guid 的列表的备注部分。</span><span class="sxs-lookup"><span data-stu-id="676d0-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="676d0-109">[out]返回选项的值。</span><span class="sxs-lookup"><span data-stu-id="676d0-109">[out] The value of the returned option.</span></span> <span data-ttu-id="676d0-110">此值的类型将指定的选项的类型的变体。</span><span class="sxs-lookup"><span data-stu-id="676d0-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="676d0-111">备注</span><span class="sxs-lookup"><span data-stu-id="676d0-111">Remarks</span></span>  
 <span data-ttu-id="676d0-112">以下列表显示了此方法支持的 Guid。</span><span class="sxs-lookup"><span data-stu-id="676d0-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="676d0-113">有关说明，请参阅[imetadatadispenserex:: Setoption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="676d0-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="676d0-114">如果`optionId`是不在此列表中，此方法返回 HRESULT `E_INVALIDARG`，指示存在错误的参数。</span><span class="sxs-lookup"><span data-stu-id="676d0-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="676d0-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="676d0-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="676d0-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="676d0-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="676d0-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="676d0-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="676d0-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="676d0-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="676d0-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="676d0-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="676d0-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="676d0-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="676d0-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="676d0-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="676d0-122">要求</span><span class="sxs-lookup"><span data-stu-id="676d0-122">Requirements</span></span>  
 <span data-ttu-id="676d0-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="676d0-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="676d0-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="676d0-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="676d0-125">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="676d0-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="676d0-126">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="676d0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676d0-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="676d0-127">See also</span></span>
- [<span data-ttu-id="676d0-128">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="676d0-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="676d0-129">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="676d0-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
