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
ms.openlocfilehash: 832adacac4a6df9ccf21578538a1c557150f3ba1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008776"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="6d894-102">IMetaDataDispenserEx::GetOption 方法</span><span class="sxs-lookup"><span data-stu-id="6d894-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="6d894-103">为当前元数据范围获取指定选项的值。</span><span class="sxs-lookup"><span data-stu-id="6d894-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="6d894-104">选项控制如何处理对当前元数据范围的调用。</span><span class="sxs-lookup"><span data-stu-id="6d894-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d894-105">语法</span><span class="sxs-lookup"><span data-stu-id="6d894-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d894-106">参数</span><span class="sxs-lookup"><span data-stu-id="6d894-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="6d894-107">中指向 GUID 的指针，该 GUID 指定要检索的选项。</span><span class="sxs-lookup"><span data-stu-id="6d894-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="6d894-108">有关支持的 Guid 的列表，请参阅 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="6d894-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6d894-109">弄返回的选项的值。</span><span class="sxs-lookup"><span data-stu-id="6d894-109">[out] The value of the returned option.</span></span> <span data-ttu-id="6d894-110">此值的类型将是指定选项的类型的变体。</span><span class="sxs-lookup"><span data-stu-id="6d894-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d894-111">备注</span><span class="sxs-lookup"><span data-stu-id="6d894-111">Remarks</span></span>  
 <span data-ttu-id="6d894-112">以下列表显示了此方法支持的 Guid。</span><span class="sxs-lookup"><span data-stu-id="6d894-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="6d894-113">有关说明，请参阅[IMetaDataDispenserEx：： SetOption](imetadatadispenserex-setoption-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6d894-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="6d894-114">如果不 `optionId` 在此列表中，则此方法返回 HRESULT `E_INVALIDARG` ，指示参数不正确。</span><span class="sxs-lookup"><span data-stu-id="6d894-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="6d894-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="6d894-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="6d894-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="6d894-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="6d894-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="6d894-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="6d894-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="6d894-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="6d894-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="6d894-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="6d894-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="6d894-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="6d894-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="6d894-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d894-122">要求</span><span class="sxs-lookup"><span data-stu-id="6d894-122">Requirements</span></span>  
 <span data-ttu-id="6d894-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d894-123">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d894-124">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="6d894-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d894-125">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d894-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d894-126">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d894-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d894-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d894-127">See also</span></span>

- [<span data-ttu-id="6d894-128">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="6d894-128">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="6d894-129">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="6d894-129">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
