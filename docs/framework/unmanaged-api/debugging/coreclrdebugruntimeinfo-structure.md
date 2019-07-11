---
title: CoreClrDebugRuntimeInfo 结构
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b58832e110f67a54d3bd57a7284b2e26e43d6bf7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739406"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="ea5f3-102">CoreClrDebugRuntimeInfo 结构</span><span class="sxs-lookup"><span data-stu-id="ea5f3-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="ea5f3-103">表示公共语言运行时 (CLR) 实例，该实例加载到远程计算机上的进程中。</span><span class="sxs-lookup"><span data-stu-id="ea5f3-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea5f3-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="ea5f3-105">成员</span><span class="sxs-lookup"><span data-stu-id="ea5f3-105">Members</span></span>  
  
|<span data-ttu-id="ea5f3-106">成员</span><span class="sxs-lookup"><span data-stu-id="ea5f3-106">Member</span></span>|<span data-ttu-id="ea5f3-107">描述</span><span class="sxs-lookup"><span data-stu-id="ea5f3-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="ea5f3-108">由运行在目标计算机上的远程调试代理分配的运行时标识符。</span><span class="sxs-lookup"><span data-stu-id="ea5f3-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea5f3-109">要求</span><span class="sxs-lookup"><span data-stu-id="ea5f3-109">Requirements</span></span>  
 <span data-ttu-id="ea5f3-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea5f3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea5f3-111">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ea5f3-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ea5f3-112">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ea5f3-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ea5f3-113">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ea5f3-113">**.NET Framework Versions:** 3.5 SP1</span></span>
