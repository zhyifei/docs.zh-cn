---
title: GetDemultiplexedStub 函数（非托管 API 参考）
description: GetDemultiplexedStub 函数创建对象转发器接收器，以帮助客户端接收来自 Windows 管理的异步调用。
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2d3885a4a9e54950909053ba18de5b1891e7edf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798612"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="f43be-103">GetDemultiplexedStub 函数</span><span class="sxs-lookup"><span data-stu-id="f43be-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="f43be-104">创建对象转发器接收器，帮助客户端从 Windows Management 接收异步调用。</span><span class="sxs-lookup"><span data-stu-id="f43be-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f43be-105">语法</span><span class="sxs-lookup"><span data-stu-id="f43be-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="f43be-106">参数</span><span class="sxs-lookup"><span data-stu-id="f43be-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="f43be-107">中一个指针，指向客户端的[IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)的进程内实现。</span><span class="sxs-lookup"><span data-stu-id="f43be-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="f43be-108">中指示事件是否为本地（`true`）的标志; `false`否则为。</span><span class="sxs-lookup"><span data-stu-id="f43be-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="f43be-109">弄用于帮助客户端从 Windows 管理接收异步调用的对象转发器接收器。</span><span class="sxs-lookup"><span data-stu-id="f43be-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="f43be-110">返回值</span><span class="sxs-lookup"><span data-stu-id="f43be-110">Return value</span></span>

<span data-ttu-id="f43be-111">如果该函数成功，则返回值为`S_OK` （0）。</span><span class="sxs-lookup"><span data-stu-id="f43be-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="f43be-112">如果函数失败，则返回值为非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="f43be-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="f43be-113">若要获取扩展的错误信息，请调用[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f43be-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="f43be-114">要求</span><span class="sxs-lookup"><span data-stu-id="f43be-114">Requirements</span></span>  
 <span data-ttu-id="f43be-115">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f43be-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f43be-116">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f43be-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f43be-117">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f43be-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43be-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f43be-118">See also</span></span>

- [<span data-ttu-id="f43be-119">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="f43be-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
