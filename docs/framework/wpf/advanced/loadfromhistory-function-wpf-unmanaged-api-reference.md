---
title: 负载从历史函数 - WPF 非托管 API 引用
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141570"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="61c07-102">从历史加载函数（WPF 非托管 API 引用）</span><span class="sxs-lookup"><span data-stu-id="61c07-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="61c07-103">此 API 支持 Windows 演示基础 （WPF） 基础结构，不用于直接从代码中使用。</span><span class="sxs-lookup"><span data-stu-id="61c07-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="61c07-104">由 Windows 演示基础 （WPF） 基础结构用于窗口管理。</span><span class="sxs-lookup"><span data-stu-id="61c07-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61c07-105">语法</span><span class="sxs-lookup"><span data-stu-id="61c07-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="61c07-106">parameters</span><span class="sxs-lookup"><span data-stu-id="61c07-106">Parameters</span></span>  
 <span data-ttu-id="61c07-107">p历史流</span><span class="sxs-lookup"><span data-stu-id="61c07-107">pHistoryStream</span></span>  
 <span data-ttu-id="61c07-108">指向历史记录信息流的指针。</span><span class="sxs-lookup"><span data-stu-id="61c07-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="61c07-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="61c07-109">pBindCtx</span></span>  
 <span data-ttu-id="61c07-110">指向绑定上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="61c07-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61c07-111">要求</span><span class="sxs-lookup"><span data-stu-id="61c07-111">Requirements</span></span>  
 <span data-ttu-id="61c07-112">**平台：** 请参阅[.NET 框架系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61c07-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61c07-113">**Dll：**</span><span class="sxs-lookup"><span data-stu-id="61c07-113">**DLL:**</span></span>  
  
 <span data-ttu-id="61c07-114">在 .NET 框架 3.0 和 3.5 中：演示HostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="61c07-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="61c07-115">在 .NET 框架 4 及更高版本：PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="61c07-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="61c07-116">**.NET 框架版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61c07-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c07-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61c07-117">See also</span></span>

- [<span data-ttu-id="61c07-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="61c07-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
