---
title: "ForwardTranslateAccelerator 函数 （WPF 非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ForwardTranslateAccelerator
api_location: PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 663b28ed1a9430a6280ccd0ee9a44da2dea0c3cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="247ca-102">ForwardTranslateAccelerator 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="247ca-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="247ca-103">此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="247ca-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="247ca-104">Windows Presentation Foundation (WPF) 基础结构用于 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="247ca-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="247ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="247ca-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="247ca-106">参数</span><span class="sxs-lookup"><span data-stu-id="247ca-106">Parameters</span></span>  
 <span data-ttu-id="247ca-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="247ca-107">pMsg</span></span>  
 <span data-ttu-id="247ca-108">一条消息指向的指针。</span><span class="sxs-lookup"><span data-stu-id="247ca-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="247ca-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="247ca-109">appUnhandled</span></span>  
 <span data-ttu-id="247ca-110">`true`当应用程序已被授予一个机会处理输入的消息，但不是处理它;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="247ca-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="247ca-111">要求</span><span class="sxs-lookup"><span data-stu-id="247ca-111">Requirements</span></span>  
 <span data-ttu-id="247ca-112">**平台：**请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="247ca-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="247ca-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="247ca-113">**DLL:**</span></span>  
  
 <span data-ttu-id="247ca-114">在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="247ca-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="247ca-115">在.NET Framework 4 及更高版本： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="247ca-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="247ca-116">**.NET framework 版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="247ca-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247ca-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="247ca-117">See Also</span></span>  
 [<span data-ttu-id="247ca-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="247ca-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
