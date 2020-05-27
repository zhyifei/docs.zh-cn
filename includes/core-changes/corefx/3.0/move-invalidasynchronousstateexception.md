---
ms.openlocfilehash: 78678b4b352bb063d1521e9aee3492c0cee059b8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721369"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="d7a2e-101">InvalidAsynchronousStateException 已移到另一程序集</span><span class="sxs-lookup"><span data-stu-id="d7a2e-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="d7a2e-102"><xref:System.ComponentModel.InvalidAsynchronousStateException> 类已移动。</span><span class="sxs-lookup"><span data-stu-id="d7a2e-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d7a2e-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="d7a2e-103">Change description</span></span>

<span data-ttu-id="d7a2e-104">在 .NET Core 2.2 及更低版本中，<xref:System.ComponentModel.InvalidAsynchronousStateException> 位于 System.ComponentModel.TypeConverter 程序集中  。</span><span class="sxs-lookup"><span data-stu-id="d7a2e-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="d7a2e-105">而自 .NET Core 3.0 起，它位于 System.ComponentModel.Primitives 程序集中  。</span><span class="sxs-lookup"><span data-stu-id="d7a2e-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d7a2e-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d7a2e-106">Version introduced</span></span>

<span data-ttu-id="d7a2e-107">3.0</span><span class="sxs-lookup"><span data-stu-id="d7a2e-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d7a2e-108">建议操作</span><span class="sxs-lookup"><span data-stu-id="d7a2e-108">Recommended action</span></span>

<span data-ttu-id="d7a2e-109">此更改仅影响这样的应用程序，它们通过调用 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 等方法或调用假设类型位于特定程序集中的 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 的重载，使用反射过程来加载 <xref:System.ComponentModel.InvalidAsynchronousStateException>。</span><span class="sxs-lookup"><span data-stu-id="d7a2e-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="d7a2e-110">如果是这种情况，可以更新在方法调用中引用的程序集，以反映出类型的新程序集位置。</span><span class="sxs-lookup"><span data-stu-id="d7a2e-110">If that is the case, update the assembly referenced in the method call to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="d7a2e-111">类别</span><span class="sxs-lookup"><span data-stu-id="d7a2e-111">Category</span></span>

<span data-ttu-id="d7a2e-112">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="d7a2e-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d7a2e-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="d7a2e-113">Affected APIs</span></span>

<span data-ttu-id="d7a2e-114">无。</span><span class="sxs-lookup"><span data-stu-id="d7a2e-114">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
