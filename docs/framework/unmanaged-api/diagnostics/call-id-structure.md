---
title: CALL_ID 结构
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8d6b16f3eeb32e41f3568e0b237f18c945a8cb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423892"
---
# <a name="callid-structure"></a><span data-ttu-id="0019f-102">CALL_ID 结构</span><span class="sxs-lookup"><span data-stu-id="0019f-102">CALL_ID Structure</span></span>
<span data-ttu-id="0019f-103">提供给正在调用的函数有关调试器的信息。</span><span class="sxs-lookup"><span data-stu-id="0019f-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="0019f-104">请参阅[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)有关详细信息的接口。</span><span class="sxs-lookup"><span data-stu-id="0019f-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0019f-105">语法</span><span class="sxs-lookup"><span data-stu-id="0019f-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0019f-106">成员</span><span class="sxs-lookup"><span data-stu-id="0019f-106">Members</span></span>  
  
|<span data-ttu-id="0019f-107">成员</span><span class="sxs-lookup"><span data-stu-id="0019f-107">Member</span></span>|<span data-ttu-id="0019f-108">描述</span><span class="sxs-lookup"><span data-stu-id="0019f-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="0019f-109">标识进行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="0019f-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="0019f-110">标识计算机处理器。</span><span class="sxs-lookup"><span data-stu-id="0019f-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="0019f-111">标识正在执行调用的线程。</span><span class="sxs-lookup"><span data-stu-id="0019f-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="0019f-112">指定的调用堆栈的地址。</span><span class="sxs-lookup"><span data-stu-id="0019f-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="0019f-113">指定的调用的地址。</span><span class="sxs-lookup"><span data-stu-id="0019f-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="0019f-114">标识将执行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="0019f-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0019f-115">要求</span><span class="sxs-lookup"><span data-stu-id="0019f-115">Requirements</span></span>  
 <span data-ttu-id="0019f-116">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0019f-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0019f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0019f-117">See Also</span></span>  
 [<span data-ttu-id="0019f-118">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="0019f-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="0019f-119">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="0019f-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
