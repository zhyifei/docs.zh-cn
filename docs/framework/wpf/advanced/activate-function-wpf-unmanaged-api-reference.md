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
ms.openlocfilehash: 6410b05a1b858a7b75c9bff3220d47505beabd7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357269"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="bed7b-102">激活函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="bed7b-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="bed7b-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="bed7b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="bed7b-104">Windows Presentation Foundation (WPF) 基础结构使用的 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="bed7b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed7b-105">语法</span><span class="sxs-lookup"><span data-stu-id="bed7b-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bed7b-106">参数</span><span class="sxs-lookup"><span data-stu-id="bed7b-106">Parameters</span></span>  
 <span data-ttu-id="bed7b-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="bed7b-107">pParameters</span></span>  
 <span data-ttu-id="bed7b-108">指向窗口的激活参数的指针。</span><span class="sxs-lookup"><span data-stu-id="bed7b-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="bed7b-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="bed7b-109">ppInner</span></span>  
 <span data-ttu-id="bed7b-110">指向包含一个指向单个元素缓冲区的地址的指针<xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="bed7b-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bed7b-111">要求</span><span class="sxs-lookup"><span data-stu-id="bed7b-111">Requirements</span></span>  
 <span data-ttu-id="bed7b-112">**平台：** 请参阅[.NET Framework 系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bed7b-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bed7b-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="bed7b-113">**DLL:**</span></span>  
  
 <span data-ttu-id="bed7b-114">在.NET Framework 3.0 和 3.5:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="bed7b-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="bed7b-115">在.NET Framework 4 及更高版本：PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="bed7b-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="bed7b-116">**.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bed7b-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed7b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="bed7b-117">See also</span></span>
- [<span data-ttu-id="bed7b-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="bed7b-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
