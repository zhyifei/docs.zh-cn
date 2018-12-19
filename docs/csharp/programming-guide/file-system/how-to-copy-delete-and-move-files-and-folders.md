---
title: 如何：复制、删除和移动文件和文件夹 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 498f266597032a4c35dbc8783994095b5c08fc3d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240237"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="2b200-102">如何：复制、删除和移动文件和文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2b200-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="2b200-103">以下示例演示如何从 <xref:System.IO?displayProperty=nameWithType> 命名空间使用 <xref:System.IO.File?displayProperty=nameWithType>、<xref:System.IO.Directory?displayProperty=nameWithType>、<xref:System.IO.FileInfo?displayProperty=nameWithType> 和 <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> 类以同步方式复制、移动和删除文件与文件夹。</span><span class="sxs-lookup"><span data-stu-id="2b200-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="2b200-104">这些示例未提供进度栏或其他任何用户界面。</span><span class="sxs-lookup"><span data-stu-id="2b200-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="2b200-105">若要提供标准进度对话框，请参阅[操作说明：提供文件操作进度对话框](how-to-provide-a-progress-dialog-box-for-file-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="2b200-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="2b200-106">操作多个文件时，请使用 <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> 提供事件，以便可以计算进度。</span><span class="sxs-lookup"><span data-stu-id="2b200-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="2b200-107">另一种方法是使用平台调用来调用 Windows Shell 中相应的文件相关方法。</span><span class="sxs-lookup"><span data-stu-id="2b200-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="2b200-108">有关如何异步执行这些文件操作的信息，请参阅[异步文件 I/O](../../../standard/io/asynchronous-file-i-o.md)。</span><span class="sxs-lookup"><span data-stu-id="2b200-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b200-109">示例</span><span class="sxs-lookup"><span data-stu-id="2b200-109">Example</span></span>  
 <span data-ttu-id="2b200-110">以下示例演示如何复制文件和目录。</span><span class="sxs-lookup"><span data-stu-id="2b200-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="2b200-111">示例</span><span class="sxs-lookup"><span data-stu-id="2b200-111">Example</span></span>  
 <span data-ttu-id="2b200-112">以下示例演示如何移动文件和目录。</span><span class="sxs-lookup"><span data-stu-id="2b200-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="2b200-113">示例</span><span class="sxs-lookup"><span data-stu-id="2b200-113">Example</span></span>  
 <span data-ttu-id="2b200-114">以下示例演示如何删除文件和目录。</span><span class="sxs-lookup"><span data-stu-id="2b200-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2b200-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b200-115">See Also</span></span>

- <xref:System.IO?displayProperty=nameWithType>  
- [<span data-ttu-id="2b200-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2b200-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2b200-117">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2b200-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)  
- [<span data-ttu-id="2b200-118">如何：提供文件操作进度对话框</span><span class="sxs-lookup"><span data-stu-id="2b200-118">How to: Provide a Progress Dialog Box for File Operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
- [<span data-ttu-id="2b200-119">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="2b200-119">File and Stream I/O</span></span>](../../../standard/io/index.md)  
- [<span data-ttu-id="2b200-120">通用 I/O 任务</span><span class="sxs-lookup"><span data-stu-id="2b200-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
