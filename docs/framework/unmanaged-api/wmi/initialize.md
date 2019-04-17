---
title: 初始化函数 （非托管 API 参考）
description: Initialize 函数执行 WMI 的初始化。
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c71b2b6d6f102d19d30d480ee9bafcac3c204be
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611076"
---
# <a name="initialize-function"></a><span data-ttu-id="2bfee-103">初始化函数</span><span class="sxs-lookup"><span data-stu-id="2bfee-103">Initialize function</span></span>

<span data-ttu-id="2bfee-104">执行 WMI 初始化。</span><span class="sxs-lookup"><span data-stu-id="2bfee-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="2bfee-105">语法</span><span class="sxs-lookup"><span data-stu-id="2bfee-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="2bfee-106">参数</span><span class="sxs-lookup"><span data-stu-id="2bfee-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="2bfee-107">[in]`true`以指示允许对 WMI 对象的 QueryInterface 调用;`false`否则为。</span><span class="sxs-lookup"><span data-stu-id="2bfee-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="2bfee-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2bfee-108">Return value</span></span>

<span data-ttu-id="2bfee-109">该函数始终返回`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="2bfee-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="2bfee-110">要求</span><span class="sxs-lookup"><span data-stu-id="2bfee-110">Requirements</span></span>

<span data-ttu-id="2bfee-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bfee-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="2bfee-112">**标头：** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="2bfee-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="2bfee-113">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2bfee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2bfee-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bfee-114">See also</span></span>

- [<span data-ttu-id="2bfee-115">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="2bfee-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
