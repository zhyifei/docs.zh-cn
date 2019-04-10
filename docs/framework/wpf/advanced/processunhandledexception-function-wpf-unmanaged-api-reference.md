---
title: ProcessUnhandledException 函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 0c8751454be6e0eed547c38e9d0bc7931abaec3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196965"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="669d2-102">ProcessUnhandledException 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="669d2-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="669d2-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="669d2-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="669d2-104">Windows Presentation Foundation (WPF) 基础结构用于异常处理。</span><span class="sxs-lookup"><span data-stu-id="669d2-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="669d2-105">语法</span><span class="sxs-lookup"><span data-stu-id="669d2-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="669d2-106">参数</span><span class="sxs-lookup"><span data-stu-id="669d2-106">Parameters</span></span>  
 <span data-ttu-id="669d2-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="669d2-107">errorMsg</span></span>  
 <span data-ttu-id="669d2-108">错误消息。</span><span class="sxs-lookup"><span data-stu-id="669d2-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="669d2-109">要求</span><span class="sxs-lookup"><span data-stu-id="669d2-109">Requirements</span></span>  
 <span data-ttu-id="669d2-110">**平台：** 请参阅[.NET Framework 系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="669d2-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="669d2-111">DLL:</span><span class="sxs-lookup"><span data-stu-id="669d2-111">DLL:</span></span>**  
  
 <span data-ttu-id="669d2-112">在.NET Framework 3.0 和 3.5:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="669d2-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="669d2-113">在.NET Framework 4 及更高版本：PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="669d2-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="669d2-114">.NET framework 版本：</span><span class="sxs-lookup"><span data-stu-id="669d2-114">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="669d2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="669d2-115">See also</span></span>

- [<span data-ttu-id="669d2-116">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="669d2-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
