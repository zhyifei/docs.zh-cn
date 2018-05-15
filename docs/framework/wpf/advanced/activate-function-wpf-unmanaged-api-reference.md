---
title: 激活函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 4931f64a525f14ad5b0b69c582a81cd15d98e541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="9b227-102">激活函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="9b227-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="9b227-103">此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="9b227-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="9b227-104">Windows Presentation Foundation (WPF) 基础结构用于 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="9b227-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b227-105">语法</span><span class="sxs-lookup"><span data-stu-id="9b227-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b227-106">参数</span><span class="sxs-lookup"><span data-stu-id="9b227-106">Parameters</span></span>  
 <span data-ttu-id="9b227-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="9b227-107">pParameters</span></span>  
 <span data-ttu-id="9b227-108">指向窗口的激活参数的指针。</span><span class="sxs-lookup"><span data-stu-id="9b227-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="9b227-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="9b227-109">ppInner</span></span>  
 <span data-ttu-id="9b227-110">指向包含的指针的单个元素缓冲区的地址的指针<xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="9b227-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b227-111">要求</span><span class="sxs-lookup"><span data-stu-id="9b227-111">Requirements</span></span>  
 <span data-ttu-id="9b227-112">**平台：** 请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b227-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b227-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="9b227-113">**DLL:**</span></span>  
  
 <span data-ttu-id="9b227-114">在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="9b227-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="9b227-115">在.NET Framework 4 及更高版本： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="9b227-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="9b227-116">**.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b227-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b227-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b227-117">See Also</span></span>  
 [<span data-ttu-id="9b227-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="9b227-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
