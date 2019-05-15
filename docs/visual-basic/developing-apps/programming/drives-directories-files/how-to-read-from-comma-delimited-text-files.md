---
title: 如何：在 Visual Basic 中读取逗号分隔的文本文件
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: 8b9faaad2abaa0d551304ff03f8212bd535eda58
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623221"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="4b528-102">如何：在 Visual Basic 中读取逗号分隔的文本文件</span><span class="sxs-lookup"><span data-stu-id="4b528-102">How to: read from comma-delimited text files in Visual Basic</span></span>
<span data-ttu-id="4b528-103">`TextFieldParser` 对象提供一种可以轻松而高效地分析结构化文本文件（如日志）的方法。</span><span class="sxs-lookup"><span data-stu-id="4b528-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="4b528-104">`TextFieldType` 属性用于定义文件是带分隔符的文件还是具有固定宽度文本字段的文件。</span><span class="sxs-lookup"><span data-stu-id="4b528-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="4b528-105">分析逗号分隔的文本文件</span><span class="sxs-lookup"><span data-stu-id="4b528-105">To parse a comma delimited text file</span></span>  
  
1. <span data-ttu-id="4b528-106">创建一个新的 `TextFieldParser`。</span><span class="sxs-lookup"><span data-stu-id="4b528-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="4b528-107">下面的代码创建名为 `MyReader` 的 `TextFieldParser`，并打开 `test.txt` 文件。</span><span class="sxs-lookup"><span data-stu-id="4b528-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2. <span data-ttu-id="4b528-108">定义 `TextField` 类型和分隔符。</span><span class="sxs-lookup"><span data-stu-id="4b528-108">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="4b528-109">下面的代码将 `TextFieldType` 属性定义为 `Delimited`，并将分隔符定义为“,”。</span><span class="sxs-lookup"><span data-stu-id="4b528-109">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3. <span data-ttu-id="4b528-110">循环访问文件中的各个字段。</span><span class="sxs-lookup"><span data-stu-id="4b528-110">Loop through the fields in the file.</span></span> <span data-ttu-id="4b528-111">如果遇到任何损坏的行，则报告错误，然后继续分析。</span><span class="sxs-lookup"><span data-stu-id="4b528-111">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="4b528-112">下面的代码循环访问该文件，依次显示各字段并报告所有格式不正确的字段。</span><span class="sxs-lookup"><span data-stu-id="4b528-112">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4. <span data-ttu-id="4b528-113">用 `End While` 和 `End Using` 结束 `While` 和 `Using` 块。</span><span class="sxs-lookup"><span data-stu-id="4b528-113">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a><span data-ttu-id="4b528-114">示例</span><span class="sxs-lookup"><span data-stu-id="4b528-114">Example</span></span>  
 <span data-ttu-id="4b528-115">此示例读取文件 `test.txt`。</span><span class="sxs-lookup"><span data-stu-id="4b528-115">This example reads from the file `test.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="4b528-116">可靠编程</span><span class="sxs-lookup"><span data-stu-id="4b528-116">Robust programming</span></span>  
 <span data-ttu-id="4b528-117">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="4b528-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="4b528-118">无法使用指定的格式 (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>) 分析行。</span><span class="sxs-lookup"><span data-stu-id="4b528-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="4b528-119">此异常消息指定导致发生异常的行，同时将 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> 属性分配给该行中包含的文本。</span><span class="sxs-lookup"><span data-stu-id="4b528-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
- <span data-ttu-id="4b528-120">指定的文件不存在 (<xref:System.IO.FileNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="4b528-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="4b528-121">在部分信任的情况下，用户没有足够的权限访问文件。</span><span class="sxs-lookup"><span data-stu-id="4b528-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="4b528-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="4b528-122">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="4b528-123">路径过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="4b528-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="4b528-124">用户没有足够的权限访问文件 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="4b528-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b528-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b528-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="4b528-126">如何：读取固定宽度的文本文件</span><span class="sxs-lookup"><span data-stu-id="4b528-126">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="4b528-127">如何：读取具有多种格式的文本文件</span><span class="sxs-lookup"><span data-stu-id="4b528-127">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="4b528-128">使用 TextFieldParser 对象分析文本文件</span><span class="sxs-lookup"><span data-stu-id="4b528-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="4b528-129">演练：在 Visual Basic 中操作文件和目录</span><span class="sxs-lookup"><span data-stu-id="4b528-129">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="4b528-130">排除故障：读取和写入文本文件</span><span class="sxs-lookup"><span data-stu-id="4b528-130">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
