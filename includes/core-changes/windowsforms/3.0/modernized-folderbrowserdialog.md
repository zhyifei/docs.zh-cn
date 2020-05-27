---
ms.openlocfilehash: 11c04441dcec260f0bfb90f6ed2b919b1545b382
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721214"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="e2f62-101">FolderBrowserDialog 的现代化</span><span class="sxs-lookup"><span data-stu-id="e2f62-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="e2f62-102">.NET Core 的 Windows 窗体应用程序中的 <xref:System.Windows.Forms.FolderBrowserDialog> 控件已更改。</span><span class="sxs-lookup"><span data-stu-id="e2f62-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e2f62-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="e2f62-103">Change description</span></span>

<span data-ttu-id="e2f62-104">在 .NET Framework 中，Windows 窗体对 <xref:System.Windows.Forms.FolderBrowserDialog> 控件使用以下对话框：</span><span class="sxs-lookup"><span data-stu-id="e2f62-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![.NET Framework 中的 FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="e2f62-106">在 .NET Core 3.0 中，Windows 窗体使用 Windows Vista 中引入的更新的基于 COM 的控件：</span><span class="sxs-lookup"><span data-stu-id="e2f62-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![.NET Core 中的 FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="e2f62-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="e2f62-108">Version introduced</span></span>

<span data-ttu-id="e2f62-109">3.0</span><span class="sxs-lookup"><span data-stu-id="e2f62-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e2f62-110">建议操作</span><span class="sxs-lookup"><span data-stu-id="e2f62-110">Recommended action</span></span>

<span data-ttu-id="e2f62-111">此对话框将自动升级。</span><span class="sxs-lookup"><span data-stu-id="e2f62-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="e2f62-112">如果希望保留原始对话框，请在显示对话框之前将 <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> 属性设置为 `false`，如以下代码片段所示：</span><span class="sxs-lookup"><span data-stu-id="e2f62-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="e2f62-113">类别</span><span class="sxs-lookup"><span data-stu-id="e2f62-113">Category</span></span>

<span data-ttu-id="e2f62-114">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="e2f62-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e2f62-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="e2f62-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

#### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
