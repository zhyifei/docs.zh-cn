---
ms.openlocfilehash: 0b2d3c1383246d4259c6d906ecf9dab927f4bdb1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720966"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a><span data-ttu-id="b10c8-101">默认控件字体更改为 Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="b10c8-101">Default control font changed to Segoe UI 9 pt</span></span>

#### <a name="change-description"></a><span data-ttu-id="b10c8-102">更改描述</span><span class="sxs-lookup"><span data-stu-id="b10c8-102">Change description</span></span>

<span data-ttu-id="b10c8-103">在 .NET Framework 中，<xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> 属性设置为 `Microsoft Sans Serif 8 pt`。</span><span class="sxs-lookup"><span data-stu-id="b10c8-103">In .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="b10c8-104">下图显示了使用默认字体的窗口。</span><span class="sxs-lookup"><span data-stu-id="b10c8-104">The following image shows a window that uses the default font.</span></span>

![.NET Framework 中的默认控件字体](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="b10c8-106">从 .NET Core 3.0 开始，默认字体设置为 `Segoe UI 9 pt`（与 <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType> 相同的字体）。</span><span class="sxs-lookup"><span data-stu-id="b10c8-106">Starting in .NET Core 3.0, the default font is set to `Segoe UI 9 pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="b10c8-107">作为此更改的结果，窗体和控件的大小会增加约 27%，以适应新默认字体的更大大小。</span><span class="sxs-lookup"><span data-stu-id="b10c8-107">As a result of this change, forms and controls are sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="b10c8-108">例如:</span><span class="sxs-lookup"><span data-stu-id="b10c8-108">For example:</span></span>

![.NET Core 中的默认控件字体](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="b10c8-110">此更改是为了与 [Windows 用户体验 (UX) 准则](/windows/win32/uxguide/vis-fonts#fonts-and-colors)保持一致。</span><span class="sxs-lookup"><span data-stu-id="b10c8-110">This change was made to align with [Windows user experience (UX) guidelines](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b10c8-111">引入的版本</span><span class="sxs-lookup"><span data-stu-id="b10c8-111">Version introduced</span></span>

<span data-ttu-id="b10c8-112">3.0</span><span class="sxs-lookup"><span data-stu-id="b10c8-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b10c8-113">建议操作</span><span class="sxs-lookup"><span data-stu-id="b10c8-113">Recommended action</span></span>

<span data-ttu-id="b10c8-114">由于窗体和控件的大小改变，因此请确保应用程序能够正确呈现。</span><span class="sxs-lookup"><span data-stu-id="b10c8-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="b10c8-115">要保留原始字体，请将窗体的默认字体设置为 `Microsoft Sans Serif 8 pt`。</span><span class="sxs-lookup"><span data-stu-id="b10c8-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="b10c8-116">例如:</span><span class="sxs-lookup"><span data-stu-id="b10c8-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="b10c8-117">类别</span><span class="sxs-lookup"><span data-stu-id="b10c8-117">Category</span></span>

- <span data-ttu-id="b10c8-118">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="b10c8-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b10c8-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="b10c8-119">Affected APIs</span></span>

<span data-ttu-id="b10c8-120">无。</span><span class="sxs-lookup"><span data-stu-id="b10c8-120">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
