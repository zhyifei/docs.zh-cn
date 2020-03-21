---
title: 获取当前公寓类型函数（非托管 API 参考）
description: GetCurrent公寓类型函数检索调用方正在其中执行的公寓类型。
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
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176820"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="45ca6-103">GetCurrentApartmentType 函数</span><span class="sxs-lookup"><span data-stu-id="45ca6-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="45ca6-104">检索调用方执行操作所在的单元类型。</span><span class="sxs-lookup"><span data-stu-id="45ca6-104">Retrieves the type of apartment in which the caller is executing.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="45ca6-105">语法</span><span class="sxs-lookup"><span data-stu-id="45ca6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc,
   [in] IComThreadingInfo*    ptr,
   [out] APTTYPE*             aptType
);
```  

## <a name="parameters"></a><span data-ttu-id="45ca6-106">parameters</span><span class="sxs-lookup"><span data-stu-id="45ca6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="45ca6-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="45ca6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="45ca6-108">[在]指向[IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="45ca6-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="45ca6-109">[出]指向[APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype)枚举值的指针，指示调用方的公寓。</span><span class="sxs-lookup"><span data-stu-id="45ca6-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="45ca6-110">返回值</span><span class="sxs-lookup"><span data-stu-id="45ca6-110">Return value</span></span>

|<span data-ttu-id="45ca6-111">一直</span><span class="sxs-lookup"><span data-stu-id="45ca6-111">Constant</span></span>  |<span data-ttu-id="45ca6-112">值</span><span class="sxs-lookup"><span data-stu-id="45ca6-112">Value</span></span>  |<span data-ttu-id="45ca6-113">说明</span><span class="sxs-lookup"><span data-stu-id="45ca6-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="45ca6-114">0</span><span class="sxs-lookup"><span data-stu-id="45ca6-114">0</span></span> | <span data-ttu-id="45ca6-115">功能已成功完成。</span><span class="sxs-lookup"><span data-stu-id="45ca6-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="45ca6-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="45ca6-116">0x80000008</span></span> | <span data-ttu-id="45ca6-117">调用方未在公寓中执行。</span><span class="sxs-lookup"><span data-stu-id="45ca6-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="45ca6-118">备注</span><span class="sxs-lookup"><span data-stu-id="45ca6-118">Remarks</span></span>

<span data-ttu-id="45ca6-119">此函数将调用包起来到[IComThreadingInfo：：获取当前公寓类型](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)方法。</span><span class="sxs-lookup"><span data-stu-id="45ca6-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="45ca6-120">要求</span><span class="sxs-lookup"><span data-stu-id="45ca6-120">Requirements</span></span>  
 <span data-ttu-id="45ca6-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45ca6-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45ca6-122">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="45ca6-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="45ca6-123">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="45ca6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ca6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45ca6-124">See also</span></span>

- [<span data-ttu-id="45ca6-125">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="45ca6-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
