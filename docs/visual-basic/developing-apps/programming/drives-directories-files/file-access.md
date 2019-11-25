---
title: 文件访问
ms.date: 07/20/2015
helpviewer_keywords:
- file access
- files [Visual Basic], input and output
- file access, Visual Basic
- files [Visual Basic], I/O
- file I/O classes
- data [Visual Basic], accessing from files
- files [Visual Basic], accessing
- file access, using components
- My.Computer.FileSystem object, accessing files
- I/O [Visual Basic]
- sequential access
ms.assetid: 231533bf-d049-4345-befa-3fb78fe6517d
ms.openlocfilehash: 22bcd0f1f3acb0c0ad899b83ad2d879ead948f12
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348901"
---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="99c9a-102">使用 Visual Basic 访问文件</span><span class="sxs-lookup"><span data-stu-id="99c9a-102">File Access with Visual Basic</span></span>

<span data-ttu-id="99c9a-103">`My.Computer.FileSystem` 对象提供用于处理文件和文件夹的工具。</span><span class="sxs-lookup"><span data-stu-id="99c9a-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="99c9a-104">它的属性、方法和事件使你可以创建、复制、移动、调查以及删除文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="99c9a-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="99c9a-105">`My.Computer.FileSystem` 提供的性能比 Visual Basic 为后向兼容性提供的旧版功能（`FileOpen`、`FileClose`、`Input`、`InputString`、`LineInput` 等）的性能更好。</span><span class="sxs-lookup"><span data-stu-id="99c9a-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by Visual Basic for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99c9a-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="99c9a-106">In This Section</span></span>  

 [<span data-ttu-id="99c9a-107">从文件读取</span><span class="sxs-lookup"><span data-stu-id="99c9a-107">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 <span data-ttu-id="99c9a-108">列出有关使用 `My.Computer.FileSystem` 对象读取文件的主题</span><span class="sxs-lookup"><span data-stu-id="99c9a-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="99c9a-109">写入文件</span><span class="sxs-lookup"><span data-stu-id="99c9a-109">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 <span data-ttu-id="99c9a-110">列出有关使用 `My.Computer.FileSystem` 对象写入文件的主题</span><span class="sxs-lookup"><span data-stu-id="99c9a-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="99c9a-111">创建、删除和移动文件和目录</span><span class="sxs-lookup"><span data-stu-id="99c9a-111">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="99c9a-112">列出有关使用 `My.Computer.FileSystem` 对象创建、复制、删除以及移动文件和文件夹的主题。</span><span class="sxs-lookup"><span data-stu-id="99c9a-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="99c9a-113">使用 TextFieldParser 对象分析文本文件</span><span class="sxs-lookup"><span data-stu-id="99c9a-113">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="99c9a-114">讨论如何使用 `TextFieldReader` 来解析文本文件（如日志）。</span><span class="sxs-lookup"><span data-stu-id="99c9a-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="99c9a-115">文件编码</span><span class="sxs-lookup"><span data-stu-id="99c9a-115">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 <span data-ttu-id="99c9a-116">描述文件编码及其用法。</span><span class="sxs-lookup"><span data-stu-id="99c9a-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="99c9a-117">演练：在 Visual Basic 中操作文件和目录</span><span class="sxs-lookup"><span data-stu-id="99c9a-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="99c9a-118">演示如何创建报告文件和文件夹相关信息的实用工具。</span><span class="sxs-lookup"><span data-stu-id="99c9a-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="99c9a-119">排除故障：读取和写入文本文件</span><span class="sxs-lookup"><span data-stu-id="99c9a-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="99c9a-120">列出读取和写入文本文件时遇到的常见问题，并为每个问题提供补救措施。</span><span class="sxs-lookup"><span data-stu-id="99c9a-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>
