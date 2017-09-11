---
title: "如何：复制、删除和移动文件和文件夹（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: a4cfec46e0af0056a0de20a1ed83a370cd010055
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="2276f-102">如何：复制、删除和移动文件和文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2276f-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="2276f-103">以下示例演示如何从 <xref:System.IO?displayProperty=fullName> 命名空间使用 <xref:System.IO.File?displayProperty=fullName>、<xref:System.IO.Directory?displayProperty=fullName>、<xref:System.IO.FileInfo?displayProperty=fullName> 和 <xref:System.IO.DirectoryInfo?displayProperty=fullName> 类以同步方式复制、移动和删除文件与文件夹。</span><span class="sxs-lookup"><span data-stu-id="2276f-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName>, and <xref:System.IO.DirectoryInfo?displayProperty=fullName> classes from the <xref:System.IO?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="2276f-104">这些示例未提供进度栏或其他任何用户界面。</span><span class="sxs-lookup"><span data-stu-id="2276f-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="2276f-105">如果希望提供一个标准进度对话框，请参阅[如何：提供文件操作进度对话框](how-to-provide-a-progress-dialog-box-for-file-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="2276f-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="2276f-106">操作多个文件时，请使用 <xref:System.IO.FileSystemWatcher?displayProperty=fullName> 提供事件，以便可以计算进度。</span><span class="sxs-lookup"><span data-stu-id="2276f-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=fullName> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="2276f-107">另一种方法是使用平台调用来调用 Windows Shell 中相应的文件相关方法。</span><span class="sxs-lookup"><span data-stu-id="2276f-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="2276f-108">有关如何异步执行这些文件操作的信息，请参阅[异步文件 I/O](https://msdn.microsoft.com/library/kztecsys)。</span><span class="sxs-lookup"><span data-stu-id="2276f-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2276f-109">示例</span><span class="sxs-lookup"><span data-stu-id="2276f-109">Example</span></span>  
 <span data-ttu-id="2276f-110">以下示例演示如何复制文件和目录。</span><span class="sxs-lookup"><span data-stu-id="2276f-110">The following example shows how to copy files and directories.</span></span>  
  
 <span data-ttu-id="2276f-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2276f-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="2276f-112">示例</span><span class="sxs-lookup"><span data-stu-id="2276f-112">Example</span></span>  
 <span data-ttu-id="2276f-113">以下示例演示如何移动文件和目录。</span><span class="sxs-lookup"><span data-stu-id="2276f-113">The following example shows how to move files and directories.</span></span>  
  
 <span data-ttu-id="2276f-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2276f-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="2276f-115">示例</span><span class="sxs-lookup"><span data-stu-id="2276f-115">Example</span></span>  
 <span data-ttu-id="2276f-116">以下示例演示如何删除文件和目录。</span><span class="sxs-lookup"><span data-stu-id="2276f-116">The following example shows how to delete files and directories.</span></span>  
  
 <span data-ttu-id="2276f-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2276f-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2276f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2276f-118">See Also</span></span>  
 <span data-ttu-id="2276f-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2276f-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="2276f-120">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2276f-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2276f-121">[文件系统和注册表（C# 编程指南）](index.md) </span><span class="sxs-lookup"><span data-stu-id="2276f-121">[File System and the Registry (C# Programming Guide)](index.md) </span></span>  
 <span data-ttu-id="2276f-122">[如何：提供文件操作进度对话框](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span><span class="sxs-lookup"><span data-stu-id="2276f-122">[How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span></span>  
 <span data-ttu-id="2276f-123">[文件和流 I/O](https://msdn.microsoft.com/library/k3352a4t) </span><span class="sxs-lookup"><span data-stu-id="2276f-123">[File and Stream I/O](https://msdn.microsoft.com/library/k3352a4t) </span></span>  
 [<span data-ttu-id="2276f-124">通用 I/O 任务</span><span class="sxs-lookup"><span data-stu-id="2276f-124">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)

