---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: a9c4c9d597f5cc1b172213d49a3dd5b8f1c1f671
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991378"
---
# <a name="getcustomui"></a><span data-ttu-id="bca83-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="bca83-102">GetCustomUI</span></span>
<span data-ttu-id="bca83-103">由 Presentationhost.exe 调用，用于获取主机的自定义进度和错误消息（如果已实现）。</span><span class="sxs-lookup"><span data-stu-id="bca83-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bca83-104">语法</span><span class="sxs-lookup"><span data-stu-id="bca83-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bca83-105">参数</span><span class="sxs-lookup"><span data-stu-id="bca83-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="bca83-106">弄指向包含主机提供的进度用户界面的程序集的指针。</span><span class="sxs-lookup"><span data-stu-id="bca83-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="bca83-107">弄类的名称，它是宿主提供的进度用户界面，最好[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]是具有<xref:System.Windows.Controls.Page>的文件是顶级元素。</span><span class="sxs-lookup"><span data-stu-id="bca83-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="bca83-108">此类驻留在指定`pwzProgressAssemblyName`的程序集中。</span><span class="sxs-lookup"><span data-stu-id="bca83-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="bca83-109">弄指向包含宿主提供的错误用户界面的程序集的指针。</span><span class="sxs-lookup"><span data-stu-id="bca83-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="bca83-110">弄类的名称，它是宿主提供的错误用户界面，最好是具有<xref:System.Windows.Controls.Page>的 XAML 文件是它的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="bca83-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="bca83-111">此类驻留在指定`pwzErrorAssemblyName`的程序集中。</span><span class="sxs-lookup"><span data-stu-id="bca83-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bca83-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="bca83-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="bca83-113">HRESULT：已忽略。</span><span class="sxs-lookup"><span data-stu-id="bca83-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bca83-114">备注</span><span class="sxs-lookup"><span data-stu-id="bca83-114">Remarks</span></span>  
 <span data-ttu-id="bca83-115">宿主应用程序可能有 Presentationhost.exe 的默认用户界面不符合的特定主题。</span><span class="sxs-lookup"><span data-stu-id="bca83-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="bca83-116">如果是这种情况，主机应用程序可以实现[GetCustomUI](getcustomui.md) ，将进度和错误用户界面返回到 presentationhost.exe。</span><span class="sxs-lookup"><span data-stu-id="bca83-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="bca83-117">Presentationhost.exe 在使用其默认用户界面之前，将始终调用[GetCustomUI](getcustomui.md) 。</span><span class="sxs-lookup"><span data-stu-id="bca83-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="bca83-118">此函数在 Presentationhost.exe 的初始化过程中调用一次。</span><span class="sxs-lookup"><span data-stu-id="bca83-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca83-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bca83-119">See also</span></span>

- [<span data-ttu-id="bca83-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="bca83-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
