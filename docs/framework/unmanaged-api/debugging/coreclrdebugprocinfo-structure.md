---
title: CoreClrDebugProcInfo 结构
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21fc34add4038d25d60e4728847e0d84914a14e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739425"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="aae58-102">CoreClrDebugProcInfo 结构</span><span class="sxs-lookup"><span data-stu-id="aae58-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="aae58-103">表示在远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="aae58-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae58-104">语法</span><span class="sxs-lookup"><span data-stu-id="aae58-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="aae58-105">成员</span><span class="sxs-lookup"><span data-stu-id="aae58-105">Members</span></span>  
  
|<span data-ttu-id="aae58-106">成员</span><span class="sxs-lookup"><span data-stu-id="aae58-106">Member</span></span>|<span data-ttu-id="aae58-107">描述</span><span class="sxs-lookup"><span data-stu-id="aae58-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="aae58-108">操作系统分配的进程标识符。</span><span class="sxs-lookup"><span data-stu-id="aae58-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="aae58-109">由运行在目标计算机上的远程调试代理分配的进程标识符。</span><span class="sxs-lookup"><span data-stu-id="aae58-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="aae58-110">此标识符的回收通常少于 OS 标识符。</span><span class="sxs-lookup"><span data-stu-id="aae58-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="aae58-111">进程的命令行。</span><span class="sxs-lookup"><span data-stu-id="aae58-111">Command-line of the process.</span></span> <span data-ttu-id="aae58-112">此成员可能会被截断。</span><span class="sxs-lookup"><span data-stu-id="aae58-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aae58-113">要求</span><span class="sxs-lookup"><span data-stu-id="aae58-113">Requirements</span></span>  
 <span data-ttu-id="aae58-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aae58-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aae58-115">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="aae58-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="aae58-116">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="aae58-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="aae58-117">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="aae58-117">**.NET Framework Versions:** 3.5 SP1</span></span>
