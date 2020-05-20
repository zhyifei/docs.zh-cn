---
title: ICLRMetaHost::ExitProcess 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 83cbfa097541681305ff285f21c2b6c9c6391ef8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703757"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="805f2-102">ICLRMetaHost::ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="805f2-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="805f2-103">尝试正常关闭所有加载的运行时，然后终止进程。</span><span class="sxs-lookup"><span data-stu-id="805f2-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="805f2-104">取代[CorExitProcess](corexitprocess-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="805f2-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805f2-105">语法</span><span class="sxs-lookup"><span data-stu-id="805f2-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="805f2-106">参数</span><span class="sxs-lookup"><span data-stu-id="805f2-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="805f2-107">中进程的退出代码。</span><span class="sxs-lookup"><span data-stu-id="805f2-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="805f2-108">返回值</span><span class="sxs-lookup"><span data-stu-id="805f2-108">Return Value</span></span>  
 <span data-ttu-id="805f2-109">此方法从不返回，因此其返回值未定义。</span><span class="sxs-lookup"><span data-stu-id="805f2-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="805f2-110">备注</span><span class="sxs-lookup"><span data-stu-id="805f2-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="805f2-111">要求</span><span class="sxs-lookup"><span data-stu-id="805f2-111">Requirements</span></span>  
 <span data-ttu-id="805f2-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="805f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="805f2-113">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="805f2-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="805f2-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="805f2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="805f2-115">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="805f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805f2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="805f2-116">See also</span></span>

- [<span data-ttu-id="805f2-117">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="805f2-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="805f2-118">承载</span><span class="sxs-lookup"><span data-stu-id="805f2-118">Hosting</span></span>](index.md)
