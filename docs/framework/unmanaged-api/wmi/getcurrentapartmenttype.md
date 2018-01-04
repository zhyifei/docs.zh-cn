---
title: "GetCurrentApartmentType 函数 （非托管 API 参考）"
description: "GetCurrentApartmentType 函数检索的单元在其中执行调用方的类型。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetCurrentApartmentType
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetCurrentApartmentType
helpviewer_keywords: GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a42c6c3c778dbdefd4b83621e65b81741b940ebe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="76bcd-103">GetCurrentApartmentType 函数</span><span class="sxs-lookup"><span data-stu-id="76bcd-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="76bcd-104">检索在其中执行调用方的单元的类型。</span><span class="sxs-lookup"><span data-stu-id="76bcd-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="76bcd-105">语法</span><span class="sxs-lookup"><span data-stu-id="76bcd-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="76bcd-106">参数</span><span class="sxs-lookup"><span data-stu-id="76bcd-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="76bcd-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="76bcd-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="76bcd-108">[in]指向的指针[IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="76bcd-108">[in] A pointer to an [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) instance.</span></span>

`aptType`  
<span data-ttu-id="76bcd-109">[out]指向的指针[APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx)枚举值，该值指示调用方的单元。</span><span class="sxs-lookup"><span data-stu-id="76bcd-109">[out] A pointer to an [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="76bcd-110">返回值</span><span class="sxs-lookup"><span data-stu-id="76bcd-110">Return value</span></span>


|<span data-ttu-id="76bcd-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="76bcd-111">Constant</span></span>  |<span data-ttu-id="76bcd-112">“值”</span><span class="sxs-lookup"><span data-stu-id="76bcd-112">Value</span></span>  |<span data-ttu-id="76bcd-113">描述</span><span class="sxs-lookup"><span data-stu-id="76bcd-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="76bcd-114">0</span><span class="sxs-lookup"><span data-stu-id="76bcd-114">0</span></span> | <span data-ttu-id="76bcd-115">已成功完成该函数。</span><span class="sxs-lookup"><span data-stu-id="76bcd-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="76bcd-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="76bcd-116">0x80000008</span></span> | <span data-ttu-id="76bcd-117">在单元中未执行调用方。</span><span class="sxs-lookup"><span data-stu-id="76bcd-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="76bcd-118">备注</span><span class="sxs-lookup"><span data-stu-id="76bcd-118">Remarks</span></span>

<span data-ttu-id="76bcd-119">此函数包装对的调用[IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="76bcd-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="76bcd-120">惠?</span><span class="sxs-lookup"><span data-stu-id="76bcd-120">Requirements</span></span>  
 <span data-ttu-id="76bcd-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76bcd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76bcd-122">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="76bcd-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="76bcd-123">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="76bcd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76bcd-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="76bcd-124">See also</span></span>  
[<span data-ttu-id="76bcd-125">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="76bcd-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
