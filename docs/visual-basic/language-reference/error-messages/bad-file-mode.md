---
title: "错误的文件模式"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a><span data-ttu-id="03eb6-102">错误的文件模式</span><span class="sxs-lookup"><span data-stu-id="03eb6-102">Bad file mode</span></span>
<span data-ttu-id="03eb6-103">在对文件内容进行操作中使用的语句必须是适合于该文件已打开的模式。</span><span class="sxs-lookup"><span data-stu-id="03eb6-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="03eb6-104">可能的原因包括：</span><span class="sxs-lookup"><span data-stu-id="03eb6-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="03eb6-105">A`FilePutObject`或`FileGetObject`语句指定的顺序的文件。</span><span class="sxs-lookup"><span data-stu-id="03eb6-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="03eb6-106">A`Print`语句指定的文件之外打开访问模式的`Output`或`Append`。</span><span class="sxs-lookup"><span data-stu-id="03eb6-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="03eb6-107">`Input`语句指定以外打开访问模式的文件`Input`</span><span class="sxs-lookup"><span data-stu-id="03eb6-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="03eb6-108">试图写入只读文件。</span><span class="sxs-lookup"><span data-stu-id="03eb6-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03eb6-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="03eb6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="03eb6-110">请确保`FilePutObject`和`FileGetObject`仅指文件供`Random`或`Binary`访问。</span><span class="sxs-lookup"><span data-stu-id="03eb6-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="03eb6-111">请确保`Print`指定为打开的文件`Output`或`Append`访问模式。</span><span class="sxs-lookup"><span data-stu-id="03eb6-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="03eb6-112">如果不是，使用不同的语句将数据放在文件中，或重新打开了适当的模式中的文件。</span><span class="sxs-lookup"><span data-stu-id="03eb6-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="03eb6-113">请确保`Input`指定为打开的文件`Input`。</span><span class="sxs-lookup"><span data-stu-id="03eb6-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="03eb6-114">如果不是，请使用不同的语句将数据放在文件或重新打开了适当的模式中的文件。</span><span class="sxs-lookup"><span data-stu-id="03eb6-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="03eb6-115">如果你正在编写到只读文件，更改文件的读/写状态，或不要尝试对其进行写入。</span><span class="sxs-lookup"><span data-stu-id="03eb6-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="03eb6-116">使用 `My.Computer.FileSystem` 对象中的可用功能。</span><span class="sxs-lookup"><span data-stu-id="03eb6-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03eb6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03eb6-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [<span data-ttu-id="03eb6-118">疑难解答：读取和写入文本文件</span><span class="sxs-lookup"><span data-stu-id="03eb6-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
