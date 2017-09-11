---
title: "使用 TextFieldParser 对象分析文本文件 (Visual Basic)"
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
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files, parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
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
ms.openlocfilehash: ad7407ca1928f9b4a2405bc5831777fbf965b61f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a><span data-ttu-id="dc6ff-102">使用 TextFieldParser 对象分析文本文件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc6ff-102">Parsing text files with the TextFieldParser object (Visual Basic)</span></span>
<span data-ttu-id="dc6ff-103">使用 `TextFieldParser` 对象可以分析和处理非常大的文件，这些文件的结构是以宽度分隔的文本列，如日志文件或旧版数据库信息。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-103">The `TextFieldParser` object allows you to parse and process very large file that are structured as delimited-width columns of text, such as log files or legacy database information.</span></span> <span data-ttu-id="dc6ff-104">使用 `TextFieldParser` 分析文本文件与循环访问文本文件相似，而提取文本字段的分析方法则与将分隔字符串标记化所使用的字符串操作方法相似。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-104">Parsing a text file with `TextFieldParser` is similar to iterating over a text file, while the parse method to extract fields of text is similar to string manipulation methods used to tokenize delimited strings.</span></span>  
  
## <a name="parsing-different-types-of-text-files"></a><span data-ttu-id="dc6ff-105">分析不同类型的文本文件</span><span class="sxs-lookup"><span data-stu-id="dc6ff-105">Parsing different types of text files</span></span>  
 <span data-ttu-id="dc6ff-106">文本文件包含的字段可能有多种宽度，也可能使用字符（如逗号或制表符）分隔。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-106">Text files may have fields of various width, delimited by a character such as a comma or a tab space.</span></span> <span data-ttu-id="dc6ff-107">如以下示例所示，定义 `TextFieldType` 和分隔符，该示例使用 `SetDelimiters` 方法定义制表符分隔的文本文件：</span><span class="sxs-lookup"><span data-stu-id="dc6ff-107">Define `TextFieldType` and the delimiter, as in the following example, which uses the `SetDelimiters` method to define a tab-delimited text file:</span></span>  
  
 <span data-ttu-id="dc6ff-108">[!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dc6ff-108">[!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]</span></span>  
  
 <span data-ttu-id="dc6ff-109">其他文本文件可能包含固定宽度的字段。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-109">Other text files may have field widths that are fixed.</span></span> <span data-ttu-id="dc6ff-110">在这种情况下，需要将 `TextFieldType` 定义为 `FixedWidth`，并定义各字段的宽度，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-110">In such cases, you need to define the `TextFieldType` as `FixedWidth` and define the widths of each field, as in the following example.</span></span> <span data-ttu-id="dc6ff-111">此示例使用 `SetFieldWidths` 方法定义文本列：第一列的宽度为 5 个字符，第二列的宽度为 10 个字符，第三列的宽度为 11 个字符，第四列的宽度是可变的。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-111">This example uses the `SetFieldWidths` method to define the columns of text: the first column is 5 characters wide, the second is 10, the third is 11, and the fourth is of variable width.</span></span>  
  
 <span data-ttu-id="dc6ff-112">[!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dc6ff-112">[!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]</span></span>  
  
 <span data-ttu-id="dc6ff-113">定义格式之后，即可使用 `ReadFields` 方法依次处理各行来循环访问文件。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-113">Once the format is defined, you can loop through the file, using the `ReadFields` method to process each line in turn.</span></span>  
  
 <span data-ttu-id="dc6ff-114">如果字段与指定的格式不符，则会引发 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> 异常。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-114">If a field does not match the specified format, a <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> exception is thrown.</span></span> <span data-ttu-id="dc6ff-115">引发此类异常时，`ErrorLine` 和 `ErrorLineNumber` 属性将分别包含导致此异常的文本以及该文本所在的行号。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-115">When such exceptions are thrown, the `ErrorLine` and `ErrorLineNumber` properties hold the text causing the exception and the line number of that text.</span></span>  
  
## <a name="parsing-files-with-multiple-formats"></a><span data-ttu-id="dc6ff-116">分析具有多种格式的文件</span><span class="sxs-lookup"><span data-stu-id="dc6ff-116">Parsing files with multiple formats</span></span>  
 <span data-ttu-id="dc6ff-117">在读取各字段之前，可以使用 `TextFieldParser` 对象的 `PeekChars`方法来检查字段，这样可以为字段定义多种格式并采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-117">The `PeekChars` method of the `TextFieldParser` object can be used to check each field before reading it, allowing you to define multiple formats for the fields and react accordingly.</span></span> <span data-ttu-id="dc6ff-118">有关详细信息，请参阅[如何：读取具有多种格式的文本文件](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)。</span><span class="sxs-lookup"><span data-stu-id="dc6ff-118">For more information, see [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6ff-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc6ff-119">See also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>

