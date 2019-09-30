---
ms.openlocfilehash: 82835915efa0e113e81bb09bd5062ee3252f2a64
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216971"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="4b437-101">InvalidAsynchronousStateException 已移到另一程序集</span><span class="sxs-lookup"><span data-stu-id="4b437-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="4b437-102"><xref:System.ComponentModel.InvalidAsynchronousStateException> 类已移动。</span><span class="sxs-lookup"><span data-stu-id="4b437-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4b437-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="4b437-103">Change description</span></span>

<span data-ttu-id="4b437-104">在 .NET Core 2.2 及更低版本中，<xref:System.ComponentModel.InvalidAsynchronousStateException> 位于 System.ComponentModel.TypeConverter 程序集中  。</span><span class="sxs-lookup"><span data-stu-id="4b437-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="4b437-105">而自 .NET Core 3.0 起，它位于 System.ComponentModel.Primitives 程序集中  。</span><span class="sxs-lookup"><span data-stu-id="4b437-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4b437-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="4b437-106">Version introduced</span></span>

<span data-ttu-id="4b437-107">3.0</span><span class="sxs-lookup"><span data-stu-id="4b437-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4b437-108">建议的操作</span><span class="sxs-lookup"><span data-stu-id="4b437-108">Recommended action</span></span>

<span data-ttu-id="4b437-109">此更改仅影响这样的应用程序，它们通过调用 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 等方法或调用假设类型位于特定程序集中的 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 的重载，使用反射过程来加载 <xref:System.ComponentModel.InvalidAsynchronousStateException>。</span><span class="sxs-lookup"><span data-stu-id="4b437-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="4b437-110">若是如此，应更新程序集在方法调用反射的程序集，以反射出类型的新程序集位置。</span><span class="sxs-lookup"><span data-stu-id="4b437-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="4b437-111">类别</span><span class="sxs-lookup"><span data-stu-id="4b437-111">Category</span></span>

<span data-ttu-id="4b437-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="4b437-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4b437-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="4b437-113">Affected APIs</span></span>

- <span data-ttu-id="4b437-114">无</span><span class="sxs-lookup"><span data-stu-id="4b437-114">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
