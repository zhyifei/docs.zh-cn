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
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177718"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="479fd-102">IMetaDataDispenserEx::GetOption 方法</span><span class="sxs-lookup"><span data-stu-id="479fd-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="479fd-103">获取当前元数据作用域的指定选项的值。</span><span class="sxs-lookup"><span data-stu-id="479fd-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="479fd-104">该选项控制如何处理对当前元数据作用域的调用。</span><span class="sxs-lookup"><span data-stu-id="479fd-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479fd-105">语法</span><span class="sxs-lookup"><span data-stu-id="479fd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="479fd-106">parameters</span><span class="sxs-lookup"><span data-stu-id="479fd-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="479fd-107">[在]指向 GUID 的指针，用于指定要检索的选项。</span><span class="sxs-lookup"><span data-stu-id="479fd-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="479fd-108">有关支持的 GUID 的列表，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="479fd-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="479fd-109">[出]返回的选项的值。</span><span class="sxs-lookup"><span data-stu-id="479fd-109">[out] The value of the returned option.</span></span> <span data-ttu-id="479fd-110">此值的类型将是指定选项类型的变体。</span><span class="sxs-lookup"><span data-stu-id="479fd-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="479fd-111">备注</span><span class="sxs-lookup"><span data-stu-id="479fd-111">Remarks</span></span>  
 <span data-ttu-id="479fd-112">下面的列表显示了此方法支持的 GUID。</span><span class="sxs-lookup"><span data-stu-id="479fd-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="479fd-113">有关说明，请参阅[IMetaDataDispenserEx：：SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="479fd-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="479fd-114">如果`optionId`不在此列表中，此方法将返回 HRESULT `E_INVALIDARG`，指示不正确的参数。</span><span class="sxs-lookup"><span data-stu-id="479fd-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="479fd-115">元数据检查重复项</span><span class="sxs-lookup"><span data-stu-id="479fd-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="479fd-116">元数据参考检查</span><span class="sxs-lookup"><span data-stu-id="479fd-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="479fd-117">元数据通知令牌移动</span><span class="sxs-lookup"><span data-stu-id="479fd-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="479fd-118">元数据集</span><span class="sxs-lookup"><span data-stu-id="479fd-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="479fd-119">元数据错误，如果已发出命令</span><span class="sxs-lookup"><span data-stu-id="479fd-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="479fd-120">元数据生成适配器</span><span class="sxs-lookup"><span data-stu-id="479fd-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="479fd-121">元数据链接器选项</span><span class="sxs-lookup"><span data-stu-id="479fd-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="479fd-122">要求</span><span class="sxs-lookup"><span data-stu-id="479fd-122">Requirements</span></span>  
 <span data-ttu-id="479fd-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="479fd-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="479fd-124">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="479fd-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="479fd-125">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="479fd-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="479fd-126">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479fd-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479fd-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="479fd-127">See also</span></span>

- [<span data-ttu-id="479fd-128">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="479fd-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="479fd-129">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="479fd-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
