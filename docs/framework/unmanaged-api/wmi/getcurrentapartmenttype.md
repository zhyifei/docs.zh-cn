---
title: GetCurrentApartmentType 函数 （非托管 API 参考）
description: GetCurrentApartmentType 函数检索在其中执行调用方的单元的类型。
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4de85eb310de70dc8fd61f7c06abca95ec267f87
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522520"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="75e58-103">GetCurrentApartmentType 函数</span><span class="sxs-lookup"><span data-stu-id="75e58-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="75e58-104">检索调用方执行操作所在的单元类型。</span><span class="sxs-lookup"><span data-stu-id="75e58-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="75e58-105">语法</span><span class="sxs-lookup"><span data-stu-id="75e58-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="75e58-106">参数</span><span class="sxs-lookup"><span data-stu-id="75e58-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="75e58-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="75e58-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="75e58-108">[in]一个指向[IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)实例。</span><span class="sxs-lookup"><span data-stu-id="75e58-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="75e58-109">[out]一个指向[APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype)枚举值，该值指示调用方的单元。</span><span class="sxs-lookup"><span data-stu-id="75e58-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="75e58-110">返回值</span><span class="sxs-lookup"><span data-stu-id="75e58-110">Return value</span></span>


|<span data-ttu-id="75e58-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="75e58-111">Constant</span></span>  |<span data-ttu-id="75e58-112">“值”</span><span class="sxs-lookup"><span data-stu-id="75e58-112">Value</span></span>  |<span data-ttu-id="75e58-113">描述</span><span class="sxs-lookup"><span data-stu-id="75e58-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="75e58-114">0</span><span class="sxs-lookup"><span data-stu-id="75e58-114">0</span></span> | <span data-ttu-id="75e58-115">已成功完成该函数。</span><span class="sxs-lookup"><span data-stu-id="75e58-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="75e58-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="75e58-116">0x80000008</span></span> | <span data-ttu-id="75e58-117">调用方不在一个单元执行。</span><span class="sxs-lookup"><span data-stu-id="75e58-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="75e58-118">备注</span><span class="sxs-lookup"><span data-stu-id="75e58-118">Remarks</span></span>

<span data-ttu-id="75e58-119">此函数包装对的调用[IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)方法。</span><span class="sxs-lookup"><span data-stu-id="75e58-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="75e58-120">要求</span><span class="sxs-lookup"><span data-stu-id="75e58-120">Requirements</span></span>  
 <span data-ttu-id="75e58-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75e58-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e58-122">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="75e58-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="75e58-123">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="75e58-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e58-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="75e58-124">See also</span></span>  
[<span data-ttu-id="75e58-125">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="75e58-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
