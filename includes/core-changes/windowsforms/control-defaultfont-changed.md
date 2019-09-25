---
ms.openlocfilehash: 02dbf5ccca97f5e7d2e1fada39bdf601cf37906f
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119148"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a><span data-ttu-id="381e8-101">`Control.DefaultFont` 更改为 `Segoe UI 9pt`</span><span class="sxs-lookup"><span data-stu-id="381e8-101">`Control.DefaultFont` changed to `Segoe UI 9pt`</span></span> 

#### <a name="change-description"></a><span data-ttu-id="381e8-102">更改描述</span><span class="sxs-lookup"><span data-stu-id="381e8-102">Change description</span></span>

<span data-ttu-id="381e8-103">在 .NET Framework 中，<xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> 属性设置为 `Microsoft Sans Serif 8pt`。</span><span class="sxs-lookup"><span data-stu-id="381e8-103">In the .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="381e8-104">下图显示了使用默认字体的窗口。</span><span class="sxs-lookup"><span data-stu-id="381e8-104">The following figure shows a window that uses the default font.</span></span>

![.NET Framework 中的默认控件字体](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="381e8-106">在 .NET Core 中，从 .NET Core 3.0 开始，该字体设置为 `Segoe UI 9pt`（与 <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType> 字体相同）。</span><span class="sxs-lookup"><span data-stu-id="381e8-106">In .NET Core starting with .NET Core 3.0, it is set to `Segoe UI 9pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="381e8-107">作为此更改的结果，窗体和控件的大小会增长约 27%，以适应新默认字体的更大大小。</span><span class="sxs-lookup"><span data-stu-id="381e8-107">As a result of this change, forms and controls will be sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="381e8-108">例如:</span><span class="sxs-lookup"><span data-stu-id="381e8-108">For example:</span></span>

![.NET Core 中的默认控件字体](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="381e8-110">此更改是为了与 [Windows UX 准则](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors)保持一致。</span><span class="sxs-lookup"><span data-stu-id="381e8-110">This change was made to align with [Windows UX guidelines](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="381e8-111">引入的版本</span><span class="sxs-lookup"><span data-stu-id="381e8-111">Version introduced</span></span>

<span data-ttu-id="381e8-112">3.0</span><span class="sxs-lookup"><span data-stu-id="381e8-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="381e8-113">建议的操作</span><span class="sxs-lookup"><span data-stu-id="381e8-113">Recommended action</span></span>

<span data-ttu-id="381e8-114">由于窗体和控件的大小改变，因此请确保应用程序能够正确呈现。</span><span class="sxs-lookup"><span data-stu-id="381e8-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="381e8-115">要保留原始字体，请将窗体的默认字体设置为 `Microsoft Sans Serif 8pt`。</span><span class="sxs-lookup"><span data-stu-id="381e8-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="381e8-116">例如:</span><span class="sxs-lookup"><span data-stu-id="381e8-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="381e8-117">类别</span><span class="sxs-lookup"><span data-stu-id="381e8-117">Category</span></span>

- <span data-ttu-id="381e8-118">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="381e8-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="381e8-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="381e8-119">Affected APIs</span></span>

<span data-ttu-id="381e8-120">无。</span><span class="sxs-lookup"><span data-stu-id="381e8-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->