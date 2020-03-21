---
title: 转发加速器功能 - WPF 非托管 API 引用
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186623"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="eab4f-102">转发加速器功能（WPF 非托管 API 引用）</span><span class="sxs-lookup"><span data-stu-id="eab4f-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="eab4f-103">此 API 支持 Windows 演示基础 （WPF） 基础结构，不用于直接从代码中使用。</span><span class="sxs-lookup"><span data-stu-id="eab4f-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="eab4f-104">由 Windows 演示基础 （WPF） 基础结构用于窗口管理。</span><span class="sxs-lookup"><span data-stu-id="eab4f-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eab4f-105">语法</span><span class="sxs-lookup"><span data-stu-id="eab4f-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="eab4f-106">parameters</span><span class="sxs-lookup"><span data-stu-id="eab4f-106">Parameters</span></span>  
 <span data-ttu-id="eab4f-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="eab4f-107">pMsg</span></span>  
 <span data-ttu-id="eab4f-108">指向消息的指针。</span><span class="sxs-lookup"><span data-stu-id="eab4f-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="eab4f-109">应用程序未处理</span><span class="sxs-lookup"><span data-stu-id="eab4f-109">appUnhandled</span></span>  
 <span data-ttu-id="eab4f-110">`true`当应用程序已有机会处理输入消息，但尚未处理它;否则， `false`.</span><span class="sxs-lookup"><span data-stu-id="eab4f-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eab4f-111">要求</span><span class="sxs-lookup"><span data-stu-id="eab4f-111">Requirements</span></span>  
 <span data-ttu-id="eab4f-112">**平台：** 请参阅[.NET 框架系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eab4f-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eab4f-113">**Dll：**</span><span class="sxs-lookup"><span data-stu-id="eab4f-113">**DLL:**</span></span>  
  
 <span data-ttu-id="eab4f-114">在 .NET 框架 3.0 和 3.5 中：演示HostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="eab4f-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="eab4f-115">在 .NET 框架 4 及更高版本：PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="eab4f-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="eab4f-116">**.NET 框架版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eab4f-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab4f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eab4f-117">See also</span></span>

- [<span data-ttu-id="eab4f-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="eab4f-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
