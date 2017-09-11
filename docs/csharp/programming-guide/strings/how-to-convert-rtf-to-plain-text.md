---
title: "如何：将 RTF 转换为纯文本（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], converting from RTF
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e4c7b48467f3b260526c604fa3a36fc5d80374e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a><span data-ttu-id="f57cf-102">如何：将 RTF 转换为纯文本（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f57cf-102">How to: Convert RTF to Plain Text (C# Programming Guide)</span></span>
<span data-ttu-id="f57cf-103">RTF 格式 (RTF) 是 Microsoft 在 20 世纪 80 年代末开发的一种文档格式，允许跨操作系统交换文档。</span><span class="sxs-lookup"><span data-stu-id="f57cf-103">Rich Text Format (RTF) is a document format developed by Microsoft in the late 1980s to enable the exchange of documents across operating systems.</span></span> <span data-ttu-id="f57cf-104">Microsoft Word 和写字板均可读取和写入 RTF 文档。</span><span class="sxs-lookup"><span data-stu-id="f57cf-104">Both Microsoft Word and WordPad can read and write RTF documents.</span></span> <span data-ttu-id="f57cf-105">在 .NET Framework 中，可以使用 <xref:System.Windows.Forms.RichTextBox> 控件创建一个支持 RTF 并使用户能够以一种所见即所得的方式将格式应用于文本的 word 处理器。</span><span class="sxs-lookup"><span data-stu-id="f57cf-105">In the .NET Framework, you can use the <xref:System.Windows.Forms.RichTextBox> control to create a word processor that supports RTF and enables a user to apply formatting to text in a WYSIWIG manner.</span></span>  
  
 <span data-ttu-id="f57cf-106">还可以使用 <xref:System.Windows.Forms.RichTextBox> 控件以编程方式从文档中删除 RTF 格式代码，并将其转换为纯文本。</span><span class="sxs-lookup"><span data-stu-id="f57cf-106">You can also use the <xref:System.Windows.Forms.RichTextBox> control to programmatically remove the RTF formatting codes from a document and convert it to plain text.</span></span> <span data-ttu-id="f57cf-107">无需将控件嵌入 Windows 窗体即可执行这种类型的操作。</span><span class="sxs-lookup"><span data-stu-id="f57cf-107">You do not need to embed the control in a Windows Form to perform this kind of operation.</span></span>  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a><span data-ttu-id="f57cf-108">在项目中使用 RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="f57cf-108">To use the RichTextBox control in a project</span></span>  
  
1.  <span data-ttu-id="f57cf-109">添加对 System.Windows.Forms.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="f57cf-109">Add a reference to System.Windows.Forms.dll.</span></span>  
  
2.  <span data-ttu-id="f57cf-110">为 `System.Windows.Forms` 命名空间添加一条 using 指令（可选）。</span><span class="sxs-lookup"><span data-stu-id="f57cf-110">Add a using directive for the `System.Windows.Forms` namespace (optional).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f57cf-111">示例</span><span class="sxs-lookup"><span data-stu-id="f57cf-111">Example</span></span>  
 <span data-ttu-id="f57cf-112">以下示例将示例 RTF 文件转换为纯文本。</span><span class="sxs-lookup"><span data-stu-id="f57cf-112">The following example converts a sample RTF file to plain text.</span></span> <span data-ttu-id="f57cf-113">该文件包含 RTF 格式（如字体信息）、四个 Unicode 字符和四个扩展的 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="f57cf-113">The file contains RTF formatting (such as font information), four Unicode characters, and four extended ASCII characters.</span></span> <span data-ttu-id="f57cf-114">此示例代码打开文件，将其内容传递到 <xref:System.Windows.Forms.RichTextBox> 作为 RTF，检索内容作为文本，在 <xref:System.Windows.Forms.MessageBox> 中显示文本，并将文本输出到 UTF-8 格式的文件。</span><span class="sxs-lookup"><span data-stu-id="f57cf-114">The example code opens the file, passes its content to a <xref:System.Windows.Forms.RichTextBox> as RTF, retrieves the content as text, displays the text in a <xref:System.Windows.Forms.MessageBox>, and outputs the text to a file in UTF-8 format.</span></span>  
  
 <span data-ttu-id="f57cf-115">`MessageBox` 和输出文件包含以下文本：</span><span class="sxs-lookup"><span data-stu-id="f57cf-115">The `MessageBox` and the output file contain the following text:</span></span>  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 <span data-ttu-id="f57cf-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f57cf-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span></span>  
  
 <span data-ttu-id="f57cf-117">RTF 字符以八位为单位进行编码。</span><span class="sxs-lookup"><span data-stu-id="f57cf-117">RTF characters are encoded in eight bits.</span></span> <span data-ttu-id="f57cf-118">但是，除了指定代码页中的扩展的 ASCII 字符外，用户还可以指定 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="f57cf-118">However, users can specify Unicode characters in addition to extended ASCII characters from specified code pages.</span></span> <span data-ttu-id="f57cf-119">因为 <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> 属性的类型为[字符串](../../../csharp/language-reference/keywords/string.md)，因此字符被编码为 Unicode UTF-16。</span><span class="sxs-lookup"><span data-stu-id="f57cf-119">Because the <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> property is of type [string](../../../csharp/language-reference/keywords/string.md), the characters are encoded as Unicode UTF-16.</span></span> <span data-ttu-id="f57cf-120">来自源 RTF 文档的任何扩展的 ASCII 字符和 Unicode 字符均在文本输出中进行了正确编码。</span><span class="sxs-lookup"><span data-stu-id="f57cf-120">Any extended ASCII characters and Unicode characters from the source RTF document are correctly encoded in the text output.</span></span>  
  
 <span data-ttu-id="f57cf-121">如果使用 <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> 方法将文本写入到磁盘，则文本将被编码为 UTF-8（无字节顺序标记）。</span><span class="sxs-lookup"><span data-stu-id="f57cf-121">If you use the <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> method to write the text to disk, the text will be encoded as UTF-8 (without a Byte Order Mark).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57cf-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f57cf-122">See Also</span></span>  
 <span data-ttu-id="f57cf-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f57cf-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span></span>   
 [<span data-ttu-id="f57cf-124">字符串</span><span class="sxs-lookup"><span data-stu-id="f57cf-124">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

