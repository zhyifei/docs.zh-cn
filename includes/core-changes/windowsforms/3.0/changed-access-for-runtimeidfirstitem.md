---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643927"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="74fe0-101">更改访问 AccessibleObject.RuntimeIDFirstItem 的权限</span><span class="sxs-lookup"><span data-stu-id="74fe0-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="74fe0-102">从 .NET Core 3.0 RC1 开始，`AccessibleObject.RuntimeIDFirstItem` 的可访问性已从 `protected` 更改为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="74fe0-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="74fe0-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="74fe0-103">Change description</span></span>

<span data-ttu-id="74fe0-104">从 .NET Core 3.0 预览版 4 开始，`AccessibleObject.RuntimeIDFirstItem` 字段为 `protected`。</span><span class="sxs-lookup"><span data-stu-id="74fe0-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="74fe0-105">从 .NET Core 3.0 RC1 开始，它已从 `protected` 更改为 `internal` 以符合 .NET Framework 中字段的可访问性。</span><span class="sxs-lookup"><span data-stu-id="74fe0-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="74fe0-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="74fe0-106">Version introduced</span></span>

<span data-ttu-id="74fe0-107">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="74fe0-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="74fe0-108">建议的操作</span><span class="sxs-lookup"><span data-stu-id="74fe0-108">Recommended action</span></span>

<span data-ttu-id="74fe0-109">如果开发的 .NET Core 应用的类型派生自 <xref:System.Windows.Forms.AccessibleObject>，访问 `RuntimeIDFirstItem` 字段时，此更改可能会对你产生影响。</span><span class="sxs-lookup"><span data-stu-id="74fe0-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="74fe0-110">如果是这种情况，可以按如下方式定义局部常量：</span><span class="sxs-lookup"><span data-stu-id="74fe0-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="74fe0-111">类别</span><span class="sxs-lookup"><span data-stu-id="74fe0-111">Category</span></span>

<span data-ttu-id="74fe0-112">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="74fe0-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="74fe0-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="74fe0-113">Affected APIs</span></span>

- <span data-ttu-id="74fe0-114">无法通过 API 分析检测到。</span><span class="sxs-lookup"><span data-stu-id="74fe0-114">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
