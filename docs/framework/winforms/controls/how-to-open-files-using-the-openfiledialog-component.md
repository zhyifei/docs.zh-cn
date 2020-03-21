---
title: 如何：使用 OpenFileDialog 组件打开文件
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182133"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="c15c5-102">如何：使用打开文件对话框打开文件</span><span class="sxs-lookup"><span data-stu-id="c15c5-102">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="c15c5-103">组件<xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType>将打开用于浏览和选择文件的 Windows 对话框。</span><span class="sxs-lookup"><span data-stu-id="c15c5-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="c15c5-104">要打开和读取所选文件，可以使用 方法<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType>或创建类的<xref:System.IO.StreamReader?displayProperty=nameWithType>实例。</span><span class="sxs-lookup"><span data-stu-id="c15c5-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c15c5-105">以下示例显示了这两种方法。</span><span class="sxs-lookup"><span data-stu-id="c15c5-105">The following examples show both approaches.</span></span>

<span data-ttu-id="c15c5-106">在 .NET 框架中，要获取<xref:System.Windows.Forms.FileDialog.FileName%2A>或设置该属性需要<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类授予的权限级别。</span><span class="sxs-lookup"><span data-stu-id="c15c5-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c15c5-107">这些示例运行<xref:System.Security.Permissions.FileIOPermission>权限检查，如果在部分信任上下文中运行，则由于权限不足，可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="c15c5-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="c15c5-108">有关详细信息，请参阅[代码访问安全基础知识](../../misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="c15c5-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="c15c5-109">可以从 C# 或 Visual Basic 命令行生成和运行这些示例为 .NET 框架应用。</span><span class="sxs-lookup"><span data-stu-id="c15c5-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="c15c5-110">有关详细信息，请参阅使用[csc.exe 的命令行构建](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="c15c5-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="c15c5-111">从 .NET Core 3.0 开始，您还可以从具有 .NET 核心 Windows 窗体*\<文件夹名称>.csproj*项目文件的文件夹中生成并运行 Windows .NET Core 应用示例。</span><span class="sxs-lookup"><span data-stu-id="c15c5-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="c15c5-112">示例：使用流阅读器将文件作为流读取</span><span class="sxs-lookup"><span data-stu-id="c15c5-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="c15c5-113">下面的示例使用 Windows 窗体<xref:System.Windows.Forms.Button>控件<xref:System.Windows.Forms.Control.Click>的事件处理程序打开 方法 。 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A></span><span class="sxs-lookup"><span data-stu-id="c15c5-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="c15c5-114">用户选择文件并选择 **"确定"** 后，<xref:System.IO.StreamReader>类的实例读取该文件并在窗体的文本框中显示其内容。</span><span class="sxs-lookup"><span data-stu-id="c15c5-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="c15c5-115">有关从文件流读取的详细信息，请参阅<xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>和<xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="c15c5-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="c15c5-116">示例：使用 OpenFile 从筛选的选择中打开文件</span><span class="sxs-lookup"><span data-stu-id="c15c5-116">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="c15c5-117">下面的示例使用<xref:System.Windows.Forms.Button>控件<xref:System.Windows.Forms.Control.Click>的事件处理程序<xref:System.Windows.Forms.OpenFileDialog>打开 仅显示文本文件的筛选器。</span><span class="sxs-lookup"><span data-stu-id="c15c5-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="c15c5-118">用户选择文本文件并选择 **"确定"** 后，<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>该方法将用于在记事本中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="c15c5-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="c15c5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c15c5-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="c15c5-120">打开文件对话组件</span><span class="sxs-lookup"><span data-stu-id="c15c5-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
