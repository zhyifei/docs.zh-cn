---
title: "CALL_ID 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CALL_ID
api_location: diasymreader.dll
api_type: COM
f1_keywords: CALL_ID
helpviewer_keywords: CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c44db9021a7dbf5b497db3536eddcea020e71bf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="callid-structure"></a><span data-ttu-id="952c9-102">CALL_ID 结构</span><span class="sxs-lookup"><span data-stu-id="952c9-102">CALL_ID Structure</span></span>
<span data-ttu-id="952c9-103">提供给正在调用的函数有关调试器的信息。</span><span class="sxs-lookup"><span data-stu-id="952c9-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="952c9-104">请参阅[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)有关详细信息的接口。</span><span class="sxs-lookup"><span data-stu-id="952c9-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="952c9-105">语法</span><span class="sxs-lookup"><span data-stu-id="952c9-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="952c9-106">成员</span><span class="sxs-lookup"><span data-stu-id="952c9-106">Members</span></span>  
  
|<span data-ttu-id="952c9-107">成员</span><span class="sxs-lookup"><span data-stu-id="952c9-107">Member</span></span>|<span data-ttu-id="952c9-108">描述</span><span class="sxs-lookup"><span data-stu-id="952c9-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="952c9-109">标识进行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="952c9-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="952c9-110">标识计算机处理器。</span><span class="sxs-lookup"><span data-stu-id="952c9-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="952c9-111">标识正在执行调用的线程。</span><span class="sxs-lookup"><span data-stu-id="952c9-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="952c9-112">指定的调用堆栈的地址。</span><span class="sxs-lookup"><span data-stu-id="952c9-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="952c9-113">指定的调用的地址。</span><span class="sxs-lookup"><span data-stu-id="952c9-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="952c9-114">标识将执行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="952c9-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="952c9-115">要求</span><span class="sxs-lookup"><span data-stu-id="952c9-115">Requirements</span></span>  
 <span data-ttu-id="952c9-116">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="952c9-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952c9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="952c9-117">See Also</span></span>  
 [<span data-ttu-id="952c9-118">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="952c9-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="952c9-119">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="952c9-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
