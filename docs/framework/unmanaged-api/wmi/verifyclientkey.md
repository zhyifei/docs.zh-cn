---
title: VerifyClientKey 函数 （非托管 API 参考）
description: VerifyClientKey 函数可确保客户端密钥具有正确的安全。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782481"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="5d449-103">VerifyClientKey 函数</span><span class="sxs-lookup"><span data-stu-id="5d449-103">VerifyClientKey function</span></span>
<span data-ttu-id="5d449-104">确保客户端密钥具有正确的安全性。</span><span class="sxs-lookup"><span data-stu-id="5d449-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5d449-105">语法</span><span class="sxs-lookup"><span data-stu-id="5d449-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="5d449-106">返回值</span><span class="sxs-lookup"><span data-stu-id="5d449-106">Return value</span></span>

<span data-ttu-id="5d449-107">如果函数成功，返回值是`ERROR_SUCCESS`(0)。</span><span class="sxs-lookup"><span data-stu-id="5d449-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="5d449-108">如果函数失败，返回值是在中定义了非零错误代码*WinError.h*。</span><span class="sxs-lookup"><span data-stu-id="5d449-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d449-109">要求</span><span class="sxs-lookup"><span data-stu-id="5d449-109">Requirements</span></span>  
 <span data-ttu-id="5d449-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d449-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d449-111">**标头：** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="5d449-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="5d449-112">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d449-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d449-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d449-113">See also</span></span>

- [<span data-ttu-id="5d449-114">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="5d449-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
