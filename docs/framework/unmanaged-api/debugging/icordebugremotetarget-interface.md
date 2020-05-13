---
title: ICorDebugRemoteTarget 接口
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: 4883c208468db0096bed3ff8cf4a8ed50a5d7cc6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379233"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="18e7c-102">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="18e7c-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="18e7c-103">介绍能够让开发人员在公共语言运行时 (CLR) 环境中调试基于 Silverlight 的应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="18e7c-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="18e7c-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="18e7c-105">方法</span><span class="sxs-lookup"><span data-stu-id="18e7c-105">Methods</span></span>  
  
|<span data-ttu-id="18e7c-106">方法</span><span class="sxs-lookup"><span data-stu-id="18e7c-106">Method</span></span>|<span data-ttu-id="18e7c-107">描述</span><span class="sxs-lookup"><span data-stu-id="18e7c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18e7c-108">ICorDebugRemoteTarget::GetHostName 方法</span><span class="sxs-lookup"><span data-stu-id="18e7c-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="18e7c-109">返回远程计算机的主机名或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="18e7c-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18e7c-110">备注</span><span class="sxs-lookup"><span data-stu-id="18e7c-110">Remarks</span></span>  
 <span data-ttu-id="18e7c-111">在 Windows 95、Windows 98、Windows ME 或非 x86 平台（例如 IA-64 和 AMD64）上，不支持混合模式（即托管和本机代码）调试。</span><span class="sxs-lookup"><span data-stu-id="18e7c-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18e7c-112">要求</span><span class="sxs-lookup"><span data-stu-id="18e7c-112">Requirements</span></span>  
 <span data-ttu-id="18e7c-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18e7c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18e7c-114">**标头：** Cordebug.idl .idl</span><span class="sxs-lookup"><span data-stu-id="18e7c-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="18e7c-115">**库：** ： corguids.lib</span><span class="sxs-lookup"><span data-stu-id="18e7c-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="18e7c-116">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="18e7c-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e7c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="18e7c-117">See also</span></span>

- [<span data-ttu-id="18e7c-118">ICorDebugRemote 接口</span><span class="sxs-lookup"><span data-stu-id="18e7c-118">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="18e7c-119">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="18e7c-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="18e7c-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="18e7c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
