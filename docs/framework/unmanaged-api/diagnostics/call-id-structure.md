---
title: "CALL_ID 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 71fd69cbcced1440839b9eedf8fbe3d8f5b90646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="callid-structure"></a><span data-ttu-id="d13b3-102">CALL_ID 结构</span><span class="sxs-lookup"><span data-stu-id="d13b3-102">CALL_ID Structure</span></span>
<span data-ttu-id="d13b3-103">提供给正在调用的函数有关调试器的信息。</span><span class="sxs-lookup"><span data-stu-id="d13b3-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="d13b3-104">请参阅[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)有关详细信息的接口。</span><span class="sxs-lookup"><span data-stu-id="d13b3-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d13b3-105">语法</span><span class="sxs-lookup"><span data-stu-id="d13b3-105">Syntax</span></span>  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="d13b3-106">成员</span><span class="sxs-lookup"><span data-stu-id="d13b3-106">Members</span></span>  
  
|<span data-ttu-id="d13b3-107">成员</span><span class="sxs-lookup"><span data-stu-id="d13b3-107">Member</span></span>|<span data-ttu-id="d13b3-108">描述</span><span class="sxs-lookup"><span data-stu-id="d13b3-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="d13b3-109">标识进行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="d13b3-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="d13b3-110">标识计算机处理器。</span><span class="sxs-lookup"><span data-stu-id="d13b3-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="d13b3-111">标识正在执行调用的线程。</span><span class="sxs-lookup"><span data-stu-id="d13b3-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="d13b3-112">指定的调用堆栈的地址。</span><span class="sxs-lookup"><span data-stu-id="d13b3-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="d13b3-113">指定的调用的地址。</span><span class="sxs-lookup"><span data-stu-id="d13b3-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="d13b3-114">标识将执行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="d13b3-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d13b3-115">惠?</span><span class="sxs-lookup"><span data-stu-id="d13b3-115">Requirements</span></span>  
 <span data-ttu-id="d13b3-116">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="d13b3-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d13b3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d13b3-117">See Also</span></span>  
 [<span data-ttu-id="d13b3-118">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="d13b3-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="d13b3-119">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="d13b3-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
