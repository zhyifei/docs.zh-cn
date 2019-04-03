---
title: 错误的文件模式
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: d3d0ebd003f178567ec9e9b19d6baccb8bc15f60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819978"
---
# <a name="bad-file-mode"></a><span data-ttu-id="3538a-102">错误的文件模式</span><span class="sxs-lookup"><span data-stu-id="3538a-102">Bad file mode</span></span>
<span data-ttu-id="3538a-103">在操作文件内容中使用的语句必须是适用于在其中打开该文件的模式。</span><span class="sxs-lookup"><span data-stu-id="3538a-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="3538a-104">可能的原因包括：</span><span class="sxs-lookup"><span data-stu-id="3538a-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="3538a-105">一个`FilePutObject`或`FileGetObject`语句指定的顺序文件。</span><span class="sxs-lookup"><span data-stu-id="3538a-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="3538a-106">一个`Print`语句指定为访问模式而不打开的文件`Output`或`Append`。</span><span class="sxs-lookup"><span data-stu-id="3538a-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="3538a-107">`Input`语句指定为访问模式而不打开的文件 `Input`</span><span class="sxs-lookup"><span data-stu-id="3538a-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="3538a-108">试图写入只读文件。</span><span class="sxs-lookup"><span data-stu-id="3538a-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3538a-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3538a-109">To correct this error</span></span>  
  
-   <span data-ttu-id="3538a-110">请确保`FilePutObject`并`FileGetObject`仅指文件供`Random`或`Binary`访问。</span><span class="sxs-lookup"><span data-stu-id="3538a-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="3538a-111">请确保`Print`指定为打开的文件`Output`或`Append`访问模式。</span><span class="sxs-lookup"><span data-stu-id="3538a-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="3538a-112">如果不是，使用不同的语句将数据放在文件中，或重新打开相应的模式中的文件。</span><span class="sxs-lookup"><span data-stu-id="3538a-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="3538a-113">请确保`Input`指定为打开的文件`Input`。</span><span class="sxs-lookup"><span data-stu-id="3538a-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="3538a-114">如果没有，请使用不同的语句将数据放在文件或重新打开相应的模式中的文件。</span><span class="sxs-lookup"><span data-stu-id="3538a-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="3538a-115">如果写入只读文件时，将该文件的读/写状态更改或不尝试对其进行写入。</span><span class="sxs-lookup"><span data-stu-id="3538a-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="3538a-116">使用 `My.Computer.FileSystem` 对象中的可用功能。</span><span class="sxs-lookup"><span data-stu-id="3538a-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3538a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3538a-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="3538a-118">排除故障：读取和写入文本文件</span><span class="sxs-lookup"><span data-stu-id="3538a-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
