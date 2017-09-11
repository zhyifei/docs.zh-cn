---
title: "如何：在 Visual Basic 中读取逗号分隔的文本文件"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, parsing
- text files, tasks
- reading text files, comma-delimited
- text files, reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2ae6a3f315a8e433386319d1aa1a7f48726a19bb
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="e1e0c-102">如何：在 Visual Basic 中读取逗号分隔的文本文件</span><span class="sxs-lookup"><span data-stu-id="e1e0c-102">How to: read from comma-delimited text files in Visual Basic</span></span>
<span data-ttu-id="e1e0c-103">`TextFieldParser` 对象提供一种可以轻松而高效地分析结构化文本文件（如日志）的方法。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="e1e0c-104">`TextFieldType` 属性用于定义文件是带分隔符的文件还是具有固定宽度文本字段的文件。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="e1e0c-105">分析逗号分隔的文本文件</span><span class="sxs-lookup"><span data-stu-id="e1e0c-105">To parse a comma delimited text file</span></span>  
  
1.  <span data-ttu-id="e1e0c-106">创建一个新的 `TextFieldParser`。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="e1e0c-107">下面的代码创建名为 `MyReader` 的 `TextFieldParser`，并打开 `test.txt` 文件。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     <span data-ttu-id="e1e0c-108">[!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e1e0c-108">[!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]</span></span>  
  
2.  <span data-ttu-id="e1e0c-109">定义 `TextField` 类型和分隔符。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-109">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="e1e0c-110">下面的代码将 `TextFieldType` 属性定义为 `Delimited`，并将分隔符定义为“,”。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-110">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     <span data-ttu-id="e1e0c-111">[!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e1e0c-111">[!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]</span></span>  
  
3.  <span data-ttu-id="e1e0c-112">循环访问文件中的各个字段。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-112">Loop through the fields in the file.</span></span> <span data-ttu-id="e1e0c-113">如果遇到任何损坏的行，则报告错误，然后继续分析。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-113">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="e1e0c-114">下面的代码循环访问该文件，依次显示各字段并报告所有格式不正确的字段。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-114">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     <span data-ttu-id="e1e0c-115">[!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e1e0c-115">[!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]</span></span>  
  
4.  <span data-ttu-id="e1e0c-116">用 `End While` 和 `End Using` 结束 `While` 和 `Using` 块。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-116">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     <span data-ttu-id="e1e0c-117">[!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e1e0c-117">[!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e0c-118">示例</span><span class="sxs-lookup"><span data-stu-id="e1e0c-118">Example</span></span>  
 <span data-ttu-id="e1e0c-119">此示例读取文件 `test.txt`。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-119">This example reads from the file `test.txt`.</span></span>  
  
 <span data-ttu-id="e1e0c-120">[!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="e1e0c-120">[!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e1e0c-121">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e1e0c-121">Robust programming</span></span>  
 <span data-ttu-id="e1e0c-122">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="e1e0c-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e1e0c-123">无法使用指定的格式 (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>) 分析行。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-123">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="e1e0c-124">此异常消息指定导致发生异常的行，同时将 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> 属性分配给该行中包含的文本。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-124">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
-   <span data-ttu-id="e1e0c-125">指定的文件不存在 (<xref:System.IO.FileNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-125">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="e1e0c-126">在部分信任的情况下，用户没有足够的权限访问文件。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-126">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="e1e0c-127">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="e1e0c-127">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="e1e0c-128">路径过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-128">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="e1e0c-129">用户没有足够的权限访问文件 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="e1e0c-129">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e0c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1e0c-130">See also</span></span>  
 <span data-ttu-id="e1e0c-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e1e0c-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span></span>   
 <span data-ttu-id="e1e0c-132">[如何：读取固定宽度的文本文件](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="e1e0c-132">[How to: Read From Fixed-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span></span>  
 <span data-ttu-id="e1e0c-133">[如何：读取具有多种格式的文本文件](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span><span class="sxs-lookup"><span data-stu-id="e1e0c-133">[How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span></span>  
 <span data-ttu-id="e1e0c-134">[使用 TextFieldParser 对象分析文本文件](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span><span class="sxs-lookup"><span data-stu-id="e1e0c-134">[Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span></span>  
 <span data-ttu-id="e1e0c-135">[演练：在 Visual Basic 中操作文件和目录](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="e1e0c-135">[Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span></span>  
 [<span data-ttu-id="e1e0c-136">疑难解答：读取和写入文本文件</span><span class="sxs-lookup"><span data-stu-id="e1e0c-136">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)

