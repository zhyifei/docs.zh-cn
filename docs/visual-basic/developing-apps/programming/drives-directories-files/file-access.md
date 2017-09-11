---
title: "使用 Visual Basic 访问文件"
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
- file access
- files, input and output
- file access, Visual Basic
- files, I/O
- file I/O classes
- data [Visual Basic], accessing from files
- files, accessing
- file access, using components
- My.Computer.FileSystem object, accessing files
- I/O [Visual Basic]
- sequential access
ms.assetid: 231533bf-d049-4345-befa-3fb78fe6517d
caps.latest.revision: 17
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
ms.openlocfilehash: 71e941bf33c3b1051c22c8170b327df9fae7d4b9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="34d0c-102">使用 Visual Basic 访问文件</span><span class="sxs-lookup"><span data-stu-id="34d0c-102">File Access with Visual Basic</span></span>
<span data-ttu-id="34d0c-103">`My.Computer.FileSystem` 对象提供用于处理文件和文件夹的工具。</span><span class="sxs-lookup"><span data-stu-id="34d0c-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="34d0c-104">它的属性、方法和事件使你可以创建、复制、移动、调查以及删除文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="34d0c-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="34d0c-105">`My.Computer.FileSystem` 提供的性能比 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 为后向兼容性提供的旧版功能（`FileOpen`、`FileClose`、`Input`、`InputString`、`LineInput` 等）的性能更好。</span><span class="sxs-lookup"><span data-stu-id="34d0c-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34d0c-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="34d0c-106">In This Section</span></span>  
 [<span data-ttu-id="34d0c-107">从文件读取</span><span class="sxs-lookup"><span data-stu-id="34d0c-107">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 <span data-ttu-id="34d0c-108">列出有关使用 `My.Computer.FileSystem` 对象读取文件的主题</span><span class="sxs-lookup"><span data-stu-id="34d0c-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="34d0c-109">写入文件</span><span class="sxs-lookup"><span data-stu-id="34d0c-109">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 <span data-ttu-id="34d0c-110">列出有关使用 `My.Computer.FileSystem` 对象写入文件的主题</span><span class="sxs-lookup"><span data-stu-id="34d0c-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="34d0c-111">创建、删除和移动文件和目录</span><span class="sxs-lookup"><span data-stu-id="34d0c-111">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="34d0c-112">列出有关使用 `My.Computer.FileSystem` 对象创建、复制、删除以及移动文件和文件夹的主题。</span><span class="sxs-lookup"><span data-stu-id="34d0c-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="34d0c-113">使用 TextFieldParser 对象分析文本文件</span><span class="sxs-lookup"><span data-stu-id="34d0c-113">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="34d0c-114">讨论如何使用 `TextFieldReader` 来解析文本文件（如日志）。</span><span class="sxs-lookup"><span data-stu-id="34d0c-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="34d0c-115">文件编码</span><span class="sxs-lookup"><span data-stu-id="34d0c-115">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 <span data-ttu-id="34d0c-116">描述文件编码及其用法。</span><span class="sxs-lookup"><span data-stu-id="34d0c-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="34d0c-117">演练：在 Visual Basic 中操作文件和目录</span><span class="sxs-lookup"><span data-stu-id="34d0c-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="34d0c-118">演示如何创建报告文件和文件夹相关信息的实用工具。</span><span class="sxs-lookup"><span data-stu-id="34d0c-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="34d0c-119">疑难解答：读取和写入文本文件</span><span class="sxs-lookup"><span data-stu-id="34d0c-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="34d0c-120">列出读取和写入文本文件时遇到的常见问题，并为每个问题提供补救措施。</span><span class="sxs-lookup"><span data-stu-id="34d0c-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>

