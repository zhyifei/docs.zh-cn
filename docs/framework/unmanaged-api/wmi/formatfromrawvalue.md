---
title: 格式从原始值函数（非托管 API 引用）
description: FormatFromRawValue 函数将原始性能数据转换为指定的格式。
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0a7c0b8387f0c8e2b6e2ade94f7efeede75bd758
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176833"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="e1951-103">FormatFromRawValue 函数</span><span class="sxs-lookup"><span data-stu-id="e1951-103">FormatFromRawValue function</span></span>
<span data-ttu-id="e1951-104">如果格式转换是基于时间的，则将一个或两个原始性能数据值转换为指定格式。</span><span class="sxs-lookup"><span data-stu-id="e1951-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e1951-105">语法</span><span class="sxs-lookup"><span data-stu-id="e1951-105">Syntax</span></span>

```cpp
int FormatFromRawValue (
   [in] uint                    dwCounterType,
   [in] uint                    dwFormat,
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
);
```

## <a name="parameters"></a><span data-ttu-id="e1951-106">parameters</span><span class="sxs-lookup"><span data-stu-id="e1951-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="e1951-107">[在]计数器类型。</span><span class="sxs-lookup"><span data-stu-id="e1951-107">[in] The counter type.</span></span> <span data-ttu-id="e1951-108">有关计数器类型的列表，请参阅[WMI 性能计数器类型](/windows/desktop/WmiSdk/wmi-performance-counter-types)。</span><span class="sxs-lookup"><span data-stu-id="e1951-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="e1951-109">`dwCounterType`可以是 除`PERF_LARGE_RAW_FRACTION`和`PERF_LARGE_RAW_BASE`之外的任何计数器类型。</span><span class="sxs-lookup"><span data-stu-id="e1951-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="e1951-110">[在]要将原始性能数据转换为的格式。</span><span class="sxs-lookup"><span data-stu-id="e1951-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="e1951-111">可以为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e1951-111">It can be one of the following values:</span></span>

|<span data-ttu-id="e1951-112">一直</span><span class="sxs-lookup"><span data-stu-id="e1951-112">Constant</span></span>  |<span data-ttu-id="e1951-113">值</span><span class="sxs-lookup"><span data-stu-id="e1951-113">Value</span></span>  |<span data-ttu-id="e1951-114">说明</span><span class="sxs-lookup"><span data-stu-id="e1951-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="e1951-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="e1951-115">0x00000200</span></span> | <span data-ttu-id="e1951-116">将计算值作为双精度浮点值返回。</span><span class="sxs-lookup"><span data-stu-id="e1951-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="e1951-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="e1951-117">0x00000400</span></span> | <span data-ttu-id="e1951-118">将计算的值作为 64 位整数返回。</span><span class="sxs-lookup"><span data-stu-id="e1951-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="e1951-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="e1951-119">0x00000100</span></span> | <span data-ttu-id="e1951-120">将计算的值作为 32 位整数返回。</span><span class="sxs-lookup"><span data-stu-id="e1951-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="e1951-121">前面的值之一可以是 ORed，具有以下缩放标志之一：</span><span class="sxs-lookup"><span data-stu-id="e1951-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="e1951-122">一直</span><span class="sxs-lookup"><span data-stu-id="e1951-122">Constant</span></span>  |<span data-ttu-id="e1951-123">值</span><span class="sxs-lookup"><span data-stu-id="e1951-123">Value</span></span>  |<span data-ttu-id="e1951-124">说明</span><span class="sxs-lookup"><span data-stu-id="e1951-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="e1951-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="e1951-125">0x00001000</span></span> | <span data-ttu-id="e1951-126">不要应用计数器的缩放因子。</span><span class="sxs-lookup"><span data-stu-id="e1951-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="e1951-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="e1951-127">0x00002000</span></span> | <span data-ttu-id="e1951-128">将最终值乘以 1，000。</span><span class="sxs-lookup"><span data-stu-id="e1951-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="e1951-129">[在]指向时间基的指针，如果需要进行格式转换。</span><span class="sxs-lookup"><span data-stu-id="e1951-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="e1951-130">如果格式转换不需要时间基础信息，则忽略此参数的值。</span><span class="sxs-lookup"><span data-stu-id="e1951-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="e1951-131">[在]指向表示原始性能[`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter)值的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="e1951-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="e1951-132">[在]指向表示第二[`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter)个原始性能值的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="e1951-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="e1951-133">如果不需要第二个原始性能值，则此参数应为`null`。</span><span class="sxs-lookup"><span data-stu-id="e1951-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="e1951-134">[出]指向接收格式化性能[`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue)值的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="e1951-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="e1951-135">返回值</span><span class="sxs-lookup"><span data-stu-id="e1951-135">Return value</span></span>

<span data-ttu-id="e1951-136">此函数返回以下值：</span><span class="sxs-lookup"><span data-stu-id="e1951-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="e1951-137">一直</span><span class="sxs-lookup"><span data-stu-id="e1951-137">Constant</span></span>  |<span data-ttu-id="e1951-138">值</span><span class="sxs-lookup"><span data-stu-id="e1951-138">Value</span></span>  |<span data-ttu-id="e1951-139">说明</span><span class="sxs-lookup"><span data-stu-id="e1951-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="e1951-140">0</span><span class="sxs-lookup"><span data-stu-id="e1951-140">0</span></span> | <span data-ttu-id="e1951-141">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e1951-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="e1951-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="e1951-142">0xC0000BBD</span></span> | <span data-ttu-id="e1951-143">所需的参数丢失或不正确。</span><span class="sxs-lookup"><span data-stu-id="e1951-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="e1951-144">0xC00000BBC</span><span class="sxs-lookup"><span data-stu-id="e1951-144">0xC0000BBC</span></span> | <span data-ttu-id="e1951-145">句柄不是有效的 PDH 对象。</span><span class="sxs-lookup"><span data-stu-id="e1951-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e1951-146">备注</span><span class="sxs-lookup"><span data-stu-id="e1951-146">Remarks</span></span>

<span data-ttu-id="e1951-147">此函数将调用格式[从RawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85))函数结束。</span><span class="sxs-lookup"><span data-stu-id="e1951-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1951-148">要求</span><span class="sxs-lookup"><span data-stu-id="e1951-148">Requirements</span></span>

 <span data-ttu-id="e1951-149">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1951-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="e1951-150">**库：** 佩尔夫·德雷尔</span><span class="sxs-lookup"><span data-stu-id="e1951-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="e1951-151">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e1951-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e1951-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1951-152">See also</span></span>

- [<span data-ttu-id="e1951-153">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e1951-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
