---
ms.openlocfilehash: 5212c5d9513a8ef5f51693857d0ddb60db4e49b9
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158383"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="98a24-101">WinForms 方法现在会引发 ArgumentException</span><span class="sxs-lookup"><span data-stu-id="98a24-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="98a24-102">某些 Windows 窗体方法现在将针对无效参数引发 <xref:System.ArgumentException>，之前不会这样。</span><span class="sxs-lookup"><span data-stu-id="98a24-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="98a24-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="98a24-103">Change description</span></span>

<span data-ttu-id="98a24-104">以前，如果将异常类型或错误类型的参数传递给某些 Windows 窗体方法，会导致不确定的状态。</span><span class="sxs-lookup"><span data-stu-id="98a24-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="98a24-105">从 .NET 5.0 开始，在传递无效参数后，这些方法现在会引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="98a24-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="98a24-106">引发 <xref:System.ArgumentException> 符合 .NET 运行时的行为。</span><span class="sxs-lookup"><span data-stu-id="98a24-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="98a24-107">它还通过清楚地指示具体的无效参数来改进调试体验。</span><span class="sxs-lookup"><span data-stu-id="98a24-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="98a24-108">下表列出了受影响的方法和参数：</span><span class="sxs-lookup"><span data-stu-id="98a24-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="98a24-109">方法</span><span class="sxs-lookup"><span data-stu-id="98a24-109">Method</span></span> | <span data-ttu-id="98a24-110">参数名称</span><span class="sxs-lookup"><span data-stu-id="98a24-110">Parameter name</span></span> | <span data-ttu-id="98a24-111">条件</span><span class="sxs-lookup"><span data-stu-id="98a24-111">Condition</span></span> | <span data-ttu-id="98a24-112">新增的版本</span><span class="sxs-lookup"><span data-stu-id="98a24-112">Version added</span></span> |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="98a24-113">参数不属于 <xref:System.Windows.Forms.TabPage> 类型。</span><span class="sxs-lookup"><span data-stu-id="98a24-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="98a24-114">5.0 预览版 1</span><span class="sxs-lookup"><span data-stu-id="98a24-114">5.0 Preview 1</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="98a24-115">引入的版本</span><span class="sxs-lookup"><span data-stu-id="98a24-115">Version introduced</span></span>

<span data-ttu-id="98a24-116">.NET 5.0 预览版 1</span><span class="sxs-lookup"><span data-stu-id="98a24-116">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="98a24-117">建议操作</span><span class="sxs-lookup"><span data-stu-id="98a24-117">Recommended action</span></span>

- <span data-ttu-id="98a24-118">更新代码以防止传递无效参数。</span><span class="sxs-lookup"><span data-stu-id="98a24-118">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="98a24-119">如有必要，请在调用方法时处理 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="98a24-119">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="98a24-120">类别</span><span class="sxs-lookup"><span data-stu-id="98a24-120">Category</span></span>

<span data-ttu-id="98a24-121">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="98a24-121">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="98a24-122">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="98a24-122">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
