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
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931410"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="9b7d5-103">GetCurrentApartmentType 函数</span><span class="sxs-lookup"><span data-stu-id="9b7d5-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="9b7d5-104">检索在其中执行调用方的单元的类型。</span><span class="sxs-lookup"><span data-stu-id="9b7d5-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9b7d5-105">语法</span><span class="sxs-lookup"><span data-stu-id="9b7d5-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="9b7d5-106">参数</span><span class="sxs-lookup"><span data-stu-id="9b7d5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9b7d5-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="9b7d5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9b7d5-108">[in]一个指向[IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)实例。</span><span class="sxs-lookup"><span data-stu-id="9b7d5-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="9b7d5-109">[out]一个指向[APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype)枚举值，该值指示调用方的单元。</span><span class="sxs-lookup"><span data-stu-id="9b7d5-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="9b7d5-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9b7d5-110">Return value</span></span>


|<span data-ttu-id="9b7d5-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="9b7d5-111">Constant</span></span>  |<span data-ttu-id="9b7d5-112">“值”</span><span class="sxs-lookup"><span data-stu-id="9b7d5-112">Value</span></span>  |<span data-ttu-id="9b7d5-113">描述</span><span class="sxs-lookup"><span data-stu-id="9b7d5-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="9b7d5-114">0</span><span class="sxs-lookup"><span data-stu-id="9b7d5-114">0</span></span> | <span data-ttu-id="9b7d5-115">已成功完成该函数。</span><span class="sxs-lookup"><span data-stu-id="9b7d5-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="9b7d5-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="9b7d5-116">0x80000008</span></span> | <span data-ttu-id="9b7d5-117">调用方不在一个单元执行。</span><span class="sxs-lookup"><span data-stu-id="9b7d5-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="9b7d5-118">备注</span><span class="sxs-lookup"><span data-stu-id="9b7d5-118">Remarks</span></span>

<span data-ttu-id="9b7d5-119">此函数包装对的调用[IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)方法。</span><span class="sxs-lookup"><span data-stu-id="9b7d5-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b7d5-120">要求</span><span class="sxs-lookup"><span data-stu-id="9b7d5-120">Requirements</span></span>  
 <span data-ttu-id="9b7d5-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b7d5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b7d5-122">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9b7d5-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9b7d5-123">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9b7d5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7d5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b7d5-124">See also</span></span>  
[<span data-ttu-id="9b7d5-125">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="9b7d5-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
