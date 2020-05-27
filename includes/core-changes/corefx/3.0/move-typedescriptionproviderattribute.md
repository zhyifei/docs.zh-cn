---
ms.openlocfilehash: 7a2617f27dfd6bb527ff6d408fae6382075f24ae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721384"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="d998b-101">TypeDescriptionProviderAttribute 已移到另一程序集</span><span class="sxs-lookup"><span data-stu-id="d998b-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="d998b-102"><xref:System.ComponentModel.TypeDescriptionProviderAttribute> 类已移动。</span><span class="sxs-lookup"><span data-stu-id="d998b-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d998b-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="d998b-103">Change description</span></span>

<span data-ttu-id="d998b-104">在 .NET Core 2.2 及更低版本中，<xref:System.ComponentModel.TypeDescriptionProviderAttribute> 位于 System.ComponentModel.TypeConverter 程序集中  。</span><span class="sxs-lookup"><span data-stu-id="d998b-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="d998b-105">而自 .NET Core 3.0 起，它位于 System.ObjectModel 程序集中  。</span><span class="sxs-lookup"><span data-stu-id="d998b-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d998b-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d998b-106">Version introduced</span></span>

<span data-ttu-id="d998b-107">3.0</span><span class="sxs-lookup"><span data-stu-id="d998b-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d998b-108">建议操作</span><span class="sxs-lookup"><span data-stu-id="d998b-108">Recommended action</span></span>

<span data-ttu-id="d998b-109">此更改仅影响这样的应用程序，它们通过调用 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 等方法或调用假设类型位于特定程序集中的 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 的重载，使用反射过程来加载 <xref:System.ComponentModel.TypeDescriptionProviderAttribute> 类型。</span><span class="sxs-lookup"><span data-stu-id="d998b-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="d998b-110">若是如此，应更新在方法调用反射的程序集，以反射出类型的新程序集位置。</span><span class="sxs-lookup"><span data-stu-id="d998b-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="d998b-111">类别</span><span class="sxs-lookup"><span data-stu-id="d998b-111">Category</span></span>

<span data-ttu-id="d998b-112">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="d998b-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d998b-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="d998b-113">Affected APIs</span></span>

<span data-ttu-id="d998b-114">无。</span><span class="sxs-lookup"><span data-stu-id="d998b-114">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
