---
title: "ICorDebugRemoteTarget 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemoteTarget
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget
helpviewer_keywords: ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcfdab2857745dee7c40823ad25592de5dc833ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="e9061-102">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="e9061-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="e9061-103">介绍能够让开发人员在公共语言运行时 (CLR) 环境中调试基于 Silverlight 的应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="e9061-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9061-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9061-104">Syntax</span></span>  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e9061-105">方法</span><span class="sxs-lookup"><span data-stu-id="e9061-105">Methods</span></span>  
  
|<span data-ttu-id="e9061-106">方法</span><span class="sxs-lookup"><span data-stu-id="e9061-106">Method</span></span>|<span data-ttu-id="e9061-107">描述</span><span class="sxs-lookup"><span data-stu-id="e9061-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9061-108">ICorDebugRemoteTarget::GetHostName 方法</span><span class="sxs-lookup"><span data-stu-id="e9061-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="e9061-109">返回远程计算机的主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e9061-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9061-110">备注</span><span class="sxs-lookup"><span data-stu-id="e9061-110">Remarks</span></span>  
 <span data-ttu-id="e9061-111">在 Windows 95、Windows 98、Windows ME 或非 x86 平台（例如 IA-64 和 AMD64）上，不支持混合模式（即托管和本机代码）调试。</span><span class="sxs-lookup"><span data-stu-id="e9061-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9061-112">惠?</span><span class="sxs-lookup"><span data-stu-id="e9061-112">Requirements</span></span>  
 <span data-ttu-id="e9061-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9061-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9061-114">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="e9061-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="e9061-115">**库：** : CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9061-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9061-116">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e9061-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9061-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9061-117">See Also</span></span>  
 [<span data-ttu-id="e9061-118">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="e9061-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [<span data-ttu-id="e9061-119">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="e9061-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="e9061-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="e9061-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
