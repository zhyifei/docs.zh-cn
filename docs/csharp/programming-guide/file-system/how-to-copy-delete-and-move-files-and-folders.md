---
title: 如何复制、删除和移动文件和文件夹 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 662f0ab3b9e69aa8bfb0085f42f577b850029e4d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712268"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="fec8c-102">如何复制、删除和移动文件和文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fec8c-102">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>
<span data-ttu-id="fec8c-103">以下示例演示如何从 <xref:System.IO?displayProperty=nameWithType> 命名空间使用 <xref:System.IO.File?displayProperty=nameWithType>、<xref:System.IO.Directory?displayProperty=nameWithType>、<xref:System.IO.FileInfo?displayProperty=nameWithType> 和 <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> 类以同步方式复制、移动和删除文件与文件夹。</span><span class="sxs-lookup"><span data-stu-id="fec8c-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="fec8c-104">这些示例未提供进度栏或其他任何用户界面。</span><span class="sxs-lookup"><span data-stu-id="fec8c-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="fec8c-105">如果希望提供一个标准进度对话框，请参阅[如何提供文件操作进度对话框](how-to-provide-a-progress-dialog-box-for-file-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="fec8c-105">If you want to provide a standard progress dialog box, see [How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="fec8c-106">操作多个文件时，请使用 <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> 提供事件，以便可以计算进度。</span><span class="sxs-lookup"><span data-stu-id="fec8c-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="fec8c-107">另一种方法是使用平台调用来调用 Windows Shell 中相应的文件相关方法。</span><span class="sxs-lookup"><span data-stu-id="fec8c-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="fec8c-108">有关如何异步执行这些文件操作的信息，请参阅[异步文件 I/O](../../../standard/io/asynchronous-file-i-o.md)。</span><span class="sxs-lookup"><span data-stu-id="fec8c-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fec8c-109">示例</span><span class="sxs-lookup"><span data-stu-id="fec8c-109">Example</span></span>  
 <span data-ttu-id="fec8c-110">以下示例演示如何复制文件和目录。</span><span class="sxs-lookup"><span data-stu-id="fec8c-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="fec8c-111">示例</span><span class="sxs-lookup"><span data-stu-id="fec8c-111">Example</span></span>  
 <span data-ttu-id="fec8c-112">以下示例演示如何移动文件和目录。</span><span class="sxs-lookup"><span data-stu-id="fec8c-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="fec8c-113">示例</span><span class="sxs-lookup"><span data-stu-id="fec8c-113">Example</span></span>  
 <span data-ttu-id="fec8c-114">以下示例演示如何删除文件和目录。</span><span class="sxs-lookup"><span data-stu-id="fec8c-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="fec8c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fec8c-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="fec8c-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fec8c-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fec8c-117">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fec8c-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="fec8c-118">如何提供文件操作进度对话框</span><span class="sxs-lookup"><span data-stu-id="fec8c-118">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="fec8c-119">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="fec8c-119">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="fec8c-120">通用 I/O 任务</span><span class="sxs-lookup"><span data-stu-id="fec8c-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
