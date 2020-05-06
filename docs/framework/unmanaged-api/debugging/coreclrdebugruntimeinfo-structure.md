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
ms.openlocfilehash: 2c41e7db32ee8557a6c03217b95fd5b040655c70
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860931"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="739de-102">CoreClrDebugRuntimeInfo 结构</span><span class="sxs-lookup"><span data-stu-id="739de-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="739de-103">表示公共语言运行时 (CLR) 实例，该实例加载到远程计算机上的进程中。</span><span class="sxs-lookup"><span data-stu-id="739de-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="739de-104">语法</span><span class="sxs-lookup"><span data-stu-id="739de-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="739de-105">成员</span><span class="sxs-lookup"><span data-stu-id="739de-105">Members</span></span>  
  
|<span data-ttu-id="739de-106">成员</span><span class="sxs-lookup"><span data-stu-id="739de-106">Member</span></span>|<span data-ttu-id="739de-107">说明</span><span class="sxs-lookup"><span data-stu-id="739de-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="739de-108">由运行在目标计算机上的远程调试代理分配的运行时标识符。</span><span class="sxs-lookup"><span data-stu-id="739de-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="739de-109">要求</span><span class="sxs-lookup"><span data-stu-id="739de-109">Requirements</span></span>  
 <span data-ttu-id="739de-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="739de-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="739de-111">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="739de-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="739de-112">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="739de-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="739de-113">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="739de-113">**.NET Framework Versions:** 3.5 SP1</span></span>
