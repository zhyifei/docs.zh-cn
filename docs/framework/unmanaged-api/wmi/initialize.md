---
title: Initialize 函数（非托管 API 参考）
description: Initialize 函数执行 WMI 初始化。
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
ms.openlocfilehash: 1bc3688b30180bdcde0a87027955a789de749f90
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798437"
---
# <a name="initialize-function"></a>Initialize 函数

执行 WMI 初始化。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a>参数

`bAllowIManagementObjectQI`

中`true`表示允许对 WMI 对象上的 QueryInterface 的调用;`false`否则为。

## <a name="return-value"></a>返回值

函数始终返回`S_OK` （0）。

## <a name="requirements"></a>要求

**适用**请参阅[系统需求](../../get-started/system-requirements.md)。

**标头：** WMINet_Utils.def

**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
