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
ms.openlocfilehash: 76c852ac81126895ea3a2e1b40473722c8445201
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746553"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="b2859-103">GetCurrentApartmentType 函数</span><span class="sxs-lookup"><span data-stu-id="b2859-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="b2859-104">检索调用方执行操作所在的单元类型。</span><span class="sxs-lookup"><span data-stu-id="b2859-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b2859-105">语法</span><span class="sxs-lookup"><span data-stu-id="b2859-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="b2859-106">参数</span><span class="sxs-lookup"><span data-stu-id="b2859-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b2859-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="b2859-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b2859-108">[in]一个指向[IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)实例。</span><span class="sxs-lookup"><span data-stu-id="b2859-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="b2859-109">[out]一个指向[APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype)枚举值，该值指示调用方的单元。</span><span class="sxs-lookup"><span data-stu-id="b2859-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="b2859-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b2859-110">Return value</span></span>

|<span data-ttu-id="b2859-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="b2859-111">Constant</span></span>  |<span data-ttu-id="b2859-112">值</span><span class="sxs-lookup"><span data-stu-id="b2859-112">Value</span></span>  |<span data-ttu-id="b2859-113">Description</span><span class="sxs-lookup"><span data-stu-id="b2859-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="b2859-114">0</span><span class="sxs-lookup"><span data-stu-id="b2859-114">0</span></span> | <span data-ttu-id="b2859-115">已成功完成该函数。</span><span class="sxs-lookup"><span data-stu-id="b2859-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="b2859-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="b2859-116">0x80000008</span></span> | <span data-ttu-id="b2859-117">调用方不在一个单元执行。</span><span class="sxs-lookup"><span data-stu-id="b2859-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b2859-118">备注</span><span class="sxs-lookup"><span data-stu-id="b2859-118">Remarks</span></span>

<span data-ttu-id="b2859-119">此函数包装对的调用[IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)方法。</span><span class="sxs-lookup"><span data-stu-id="b2859-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2859-120">要求</span><span class="sxs-lookup"><span data-stu-id="b2859-120">Requirements</span></span>  
 <span data-ttu-id="b2859-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2859-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2859-122">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b2859-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b2859-123">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b2859-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2859-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2859-124">See also</span></span>

- [<span data-ttu-id="b2859-125">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="b2859-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
