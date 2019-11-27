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
ms.openlocfilehash: 8c606f67766334800444f39b115d90f65ecca13d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448591"
---
# <a name="call_id-structure"></a><span data-ttu-id="76968-102">CALL_ID 结构</span><span class="sxs-lookup"><span data-stu-id="76968-102">CALL_ID Structure</span></span>
<span data-ttu-id="76968-103">向调试器提供有关正在调用的函数的信息。</span><span class="sxs-lookup"><span data-stu-id="76968-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="76968-104">有关详细信息，请参阅[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="76968-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76968-105">语法</span><span class="sxs-lookup"><span data-stu-id="76968-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="76968-106">Members</span><span class="sxs-lookup"><span data-stu-id="76968-106">Members</span></span>  
  
|<span data-ttu-id="76968-107">成员</span><span class="sxs-lookup"><span data-stu-id="76968-107">Member</span></span>|<span data-ttu-id="76968-108">说明</span><span class="sxs-lookup"><span data-stu-id="76968-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="76968-109">标识正在进行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="76968-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="76968-110">标识计算机处理器。</span><span class="sxs-lookup"><span data-stu-id="76968-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="76968-111">标识正在执行调用的线程。</span><span class="sxs-lookup"><span data-stu-id="76968-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="76968-112">指定调用堆栈的地址。</span><span class="sxs-lookup"><span data-stu-id="76968-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="76968-113">指定调用的地址。</span><span class="sxs-lookup"><span data-stu-id="76968-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="76968-114">标识要执行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="76968-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76968-115">要求</span><span class="sxs-lookup"><span data-stu-id="76968-115">Requirements</span></span>  
 <span data-ttu-id="76968-116">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="76968-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76968-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76968-117">See also</span></span>

- [<span data-ttu-id="76968-118">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="76968-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="76968-119">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="76968-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
