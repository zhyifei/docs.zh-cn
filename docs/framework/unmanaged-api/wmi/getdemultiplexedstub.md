---
title: GetDemultiplexedStub 函数 （非托管 API 参考）
description: GetDemultiplexedStub 函数创建对象转发器接收器以帮助客户端在从 Windows 管理接收异步调用。
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
ms.openlocfilehash: 1b519ea4062682a56b5b4e277de22b14799f65d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783219"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="f2a6a-103">GetDemultiplexedStub 函数</span><span class="sxs-lookup"><span data-stu-id="f2a6a-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="f2a6a-104">创建对象转发器接收器，帮助客户端从 Windows Management 接收异步调用。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f2a6a-105">语法</span><span class="sxs-lookup"><span data-stu-id="f2a6a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="f2a6a-106">参数</span><span class="sxs-lookup"><span data-stu-id="f2a6a-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="f2a6a-107">[in]客户端的过程中实现的指针[IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="f2a6a-108">[in]一个标志，指示事件是否是本地 (`true`); 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="f2a6a-109">[out]若要帮助在异步调用从 Windows 管理的客户端对象转发器接收器。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="f2a6a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="f2a6a-110">Return value</span></span>

<span data-ttu-id="f2a6a-111">如果函数成功，返回值是`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="f2a6a-112">如果函数失败，返回值是一个非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="f2a6a-113">若要获得扩展错误信息，请调用[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="f2a6a-114">要求</span><span class="sxs-lookup"><span data-stu-id="f2a6a-114">Requirements</span></span>  
 <span data-ttu-id="f2a6a-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a6a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2a6a-116">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f2a6a-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f2a6a-117">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f2a6a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a6a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2a6a-118">See also</span></span>

- [<span data-ttu-id="f2a6a-119">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="f2a6a-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
