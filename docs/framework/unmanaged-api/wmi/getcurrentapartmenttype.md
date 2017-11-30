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
ms.openlocfilehash: b250913b55ba59261a666760cc15466b6f9d096e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="3bb15-103">GetCurrentApartmentType 函数</span><span class="sxs-lookup"><span data-stu-id="3bb15-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="3bb15-104">检索在其中执行调用方的单元的类型。</span><span class="sxs-lookup"><span data-stu-id="3bb15-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3bb15-105">语法</span><span class="sxs-lookup"><span data-stu-id="3bb15-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="3bb15-106">参数</span><span class="sxs-lookup"><span data-stu-id="3bb15-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3bb15-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="3bb15-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3bb15-108">[in]指向的指针[IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="3bb15-108">[in] A pointer to an [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) instance.</span></span>

`aptType`  
<span data-ttu-id="3bb15-109">[out]指向的指针[APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx)枚举值，该值指示调用方的单元。</span><span class="sxs-lookup"><span data-stu-id="3bb15-109">[out] A pointer to an [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="3bb15-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3bb15-110">Return value</span></span>


|<span data-ttu-id="3bb15-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="3bb15-111">Constant</span></span>  |<span data-ttu-id="3bb15-112">值</span><span class="sxs-lookup"><span data-stu-id="3bb15-112">Value</span></span>  |<span data-ttu-id="3bb15-113">描述</span><span class="sxs-lookup"><span data-stu-id="3bb15-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="3bb15-114">0</span><span class="sxs-lookup"><span data-stu-id="3bb15-114">0</span></span> | <span data-ttu-id="3bb15-115">已成功完成该函数。</span><span class="sxs-lookup"><span data-stu-id="3bb15-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="3bb15-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="3bb15-116">0x80000008</span></span> | <span data-ttu-id="3bb15-117">在单元中未执行调用方。</span><span class="sxs-lookup"><span data-stu-id="3bb15-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3bb15-118">备注</span><span class="sxs-lookup"><span data-stu-id="3bb15-118">Remarks</span></span>

<span data-ttu-id="3bb15-119">此函数包装对的调用[IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="3bb15-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3bb15-120">要求</span><span class="sxs-lookup"><span data-stu-id="3bb15-120">Requirements</span></span>  
 <span data-ttu-id="3bb15-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3bb15-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb15-122">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3bb15-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3bb15-123">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3bb15-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb15-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bb15-124">See also</span></span>  
[<span data-ttu-id="3bb15-125">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="3bb15-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
