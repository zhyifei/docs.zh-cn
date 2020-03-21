---
title: 验证客户端密钥功能（非托管 API 引用）
description: 验证客户端密钥功能可确保客户端密钥具有正确的安全性。
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176703"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="34dd9-103">验证客户端密钥功能</span><span class="sxs-lookup"><span data-stu-id="34dd9-103">VerifyClientKey function</span></span>
<span data-ttu-id="34dd9-104">确保客户端密钥具有正确的安全性。</span><span class="sxs-lookup"><span data-stu-id="34dd9-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="34dd9-105">语法</span><span class="sxs-lookup"><span data-stu-id="34dd9-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="34dd9-106">返回值</span><span class="sxs-lookup"><span data-stu-id="34dd9-106">Return value</span></span>

<span data-ttu-id="34dd9-107">如果函数成功，则返回值为`ERROR_SUCCESS`（0）。</span><span class="sxs-lookup"><span data-stu-id="34dd9-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="34dd9-108">如果函数失败，返回值是在*WinError.h*中定义的非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="34dd9-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="34dd9-109">要求</span><span class="sxs-lookup"><span data-stu-id="34dd9-109">Requirements</span></span>  
 <span data-ttu-id="34dd9-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34dd9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34dd9-111">**标题：** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="34dd9-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="34dd9-112">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="34dd9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34dd9-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34dd9-113">See also</span></span>

- [<span data-ttu-id="34dd9-114">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="34dd9-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
