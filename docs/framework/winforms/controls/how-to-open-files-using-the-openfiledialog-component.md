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
ms.openlocfilehash: 5781543a61d77ef8f0658e95759c57fdb77cfc4f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723083"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="2b545-102">如何：使用 OpenFileDialog 打开的文件</span><span class="sxs-lookup"><span data-stu-id="2b545-102">How to: Open files with the OpenFileDialog</span></span> 

<span data-ttu-id="2b545-103"><xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType>组件打开 Windows 对话框中浏览并选择文件。</span><span class="sxs-lookup"><span data-stu-id="2b545-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="2b545-104">若要打开和读取所选的文件，可以使用<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType>方法，或创建的实例<xref:System.IO.StreamReader?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="2b545-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="2b545-105">以下示例演示这两种方法。</span><span class="sxs-lookup"><span data-stu-id="2b545-105">The following examples show both approaches.</span></span> 

<span data-ttu-id="2b545-106">在.NET Framework 中，要获取或设置<xref:System.Windows.Forms.FileDialog.FileName%2A>属性需要的特权等级授予通过<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="2b545-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="2b545-107">示例运行<xref:System.Security.Permissions.FileIOPermission>权限检查，并可以在部分信任上下文中运行的情况下引发因特权不足而异常。</span><span class="sxs-lookup"><span data-stu-id="2b545-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="2b545-108">有关详细信息，请参阅[代码访问安全性基础知识](../../misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="2b545-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="2b545-109">您可以生成并运行这些示例作为从.NET Framework 应用程序C#或 Visual Basic 命令行。</span><span class="sxs-lookup"><span data-stu-id="2b545-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="2b545-110">有关详细信息，请参阅[命令行上使用 csc.exe 生成](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[中的命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="2b545-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="2b545-111">从.NET Core 3.0 开始，你还可以生成并运行示例作为 Windows.NET Core 应用程序从具有.NET Core Windows 窗体的文件夹*\<文件夹名称 >.csproj*项目文件。</span><span class="sxs-lookup"><span data-stu-id="2b545-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="2b545-112">示例:为流使用 StreamReader 读取文件</span><span class="sxs-lookup"><span data-stu-id="2b545-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="2b545-113">下面的示例使用 Windows 窗体<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序以打开<xref:System.Windows.Forms.OpenFileDialog>与<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2b545-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="2b545-114">当用户选择一个文件并选择后**确定**，实例<xref:System.IO.StreamReader>类读取文件，并在窗体的文本框中显示其内容。</span><span class="sxs-lookup"><span data-stu-id="2b545-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="2b545-115">有关从文件流读取的详细信息，请参阅<xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>和<xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2b545-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="2b545-116">示例:打开文件中使用 OpenFile 筛选选定内容</span><span class="sxs-lookup"><span data-stu-id="2b545-116">Example: Open a file from a filtered selection with OpenFile</span></span> 

<span data-ttu-id="2b545-117">下面的示例使用<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序打开<xref:System.Windows.Forms.OpenFileDialog>与筛选器，显示仅文本文件。</span><span class="sxs-lookup"><span data-stu-id="2b545-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="2b545-118">当用户选择一个文本文件，并选择后**确定**，则<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法用于在记事本中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="2b545-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="2b545-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b545-119">See also</span></span>
- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="2b545-120">OpenFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="2b545-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
