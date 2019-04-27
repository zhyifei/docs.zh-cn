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
ms.openlocfilehash: b9d4b27ca0bf454b42f15b849008e5a3019bb09a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864073"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="fdd4e-102">CoreClrDebugProcInfo 结构</span><span class="sxs-lookup"><span data-stu-id="fdd4e-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="fdd4e-103">表示在远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="fdd4e-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdd4e-104">语法</span><span class="sxs-lookup"><span data-stu-id="fdd4e-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="fdd4e-105">成员</span><span class="sxs-lookup"><span data-stu-id="fdd4e-105">Members</span></span>  
  
|<span data-ttu-id="fdd4e-106">成员</span><span class="sxs-lookup"><span data-stu-id="fdd4e-106">Member</span></span>|<span data-ttu-id="fdd4e-107">描述</span><span class="sxs-lookup"><span data-stu-id="fdd4e-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="fdd4e-108">操作系统分配的进程标识符。</span><span class="sxs-lookup"><span data-stu-id="fdd4e-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="fdd4e-109">由运行在目标计算机上的远程调试代理分配的进程标识符。</span><span class="sxs-lookup"><span data-stu-id="fdd4e-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="fdd4e-110">此标识符的回收通常少于 OS 标识符。</span><span class="sxs-lookup"><span data-stu-id="fdd4e-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="fdd4e-111">进程的命令行。</span><span class="sxs-lookup"><span data-stu-id="fdd4e-111">Command-line of the process.</span></span> <span data-ttu-id="fdd4e-112">此成员可能会被截断。</span><span class="sxs-lookup"><span data-stu-id="fdd4e-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fdd4e-113">要求</span><span class="sxs-lookup"><span data-stu-id="fdd4e-113">Requirements</span></span>  
 <span data-ttu-id="fdd4e-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fdd4e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdd4e-115">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="fdd4e-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="fdd4e-116">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="fdd4e-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="fdd4e-117">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="fdd4e-117">**.NET Framework Versions:** 3.5 SP1</span></span>
