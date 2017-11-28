---
title: "文件系统和注册表（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d1b4e3fa9b6c6da89abd242be855e9fb7c16dd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="5dbe8-102">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5dbe8-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="5dbe8-103">下面各主题介绍了如何使用 C# 和 .NET Framework 对文件、文件夹和注册表执行各种基本操作。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5dbe8-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="5dbe8-104">In This Section</span></span>  
  
|<span data-ttu-id="5dbe8-105">**标题**</span><span class="sxs-lookup"><span data-stu-id="5dbe8-105">**Title**</span></span>|<span data-ttu-id="5dbe8-106">**描述**</span><span class="sxs-lookup"><span data-stu-id="5dbe8-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="5dbe8-107">如何：循环访问目录树</span><span class="sxs-lookup"><span data-stu-id="5dbe8-107">How to: Iterate Through a Directory Tree</span></span>](../../../csharp/programming-guide/file-system/how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="5dbe8-108">介绍了如何手动循环访问目录树。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="5dbe8-109">如何：获取有关文件、文件夹和驱动器的信息</span><span class="sxs-lookup"><span data-stu-id="5dbe8-109">How to: Get Information About Files, Folders, and Drives</span></span>](../../../csharp/programming-guide/file-system/how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="5dbe8-110">介绍了如何检索有关文件、文件夹和驱动器的信息，如创建时间和大小。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="5dbe8-111">如何：创建文件或文件夹</span><span class="sxs-lookup"><span data-stu-id="5dbe8-111">How to: Create a File or Folder</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-file-or-folder.md)|<span data-ttu-id="5dbe8-112">介绍了如何新建文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="5dbe8-113">如何：复制、删除、移动文件和文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5dbe8-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="5dbe8-114">介绍了如何复制、删除、移动文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="5dbe8-115">如何：提供文件操作进度对话框</span><span class="sxs-lookup"><span data-stu-id="5dbe8-115">How to: Provide a Progress Dialog Box for File Operations</span></span>](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="5dbe8-116">介绍了如何显示特定文件操作的标准 Windows 进度对话框。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="5dbe8-117">如何：写入文本文件</span><span class="sxs-lookup"><span data-stu-id="5dbe8-117">How to: Write to a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)|<span data-ttu-id="5dbe8-118">介绍了如何将内容写入文本文件。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="5dbe8-119">如何：读取文本文件中的内容</span><span class="sxs-lookup"><span data-stu-id="5dbe8-119">How to: Read From a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-read-from-a-text-file.md)|<span data-ttu-id="5dbe8-120">介绍了如何读取文本文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="5dbe8-121">如何：一次一行地读取文本文件</span><span class="sxs-lookup"><span data-stu-id="5dbe8-121">How to: Read a Text File One Line at a Time</span></span>](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="5dbe8-122">介绍了如何一次一行地检索文件文本。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="5dbe8-123">如何：在注册表中创建注册表项</span><span class="sxs-lookup"><span data-stu-id="5dbe8-123">How to: Create a Key In the Registry</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="5dbe8-124">介绍了如何将注册表项写入系统注册表。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="5dbe8-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="5dbe8-125">Related Sections</span></span>  
 [<span data-ttu-id="5dbe8-126">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="5dbe8-126">File and Stream I/O</span></span>](https://msdn.microsoft.com/library/k3352a4t)  
  
 [<span data-ttu-id="5dbe8-127">如何：复制、删除、移动文件和文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5dbe8-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="5dbe8-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5dbe8-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
  
 [<span data-ttu-id="5dbe8-129">文件、文件夹和驱动器</span><span class="sxs-lookup"><span data-stu-id="5dbe8-129">Files, Folders and Drives</span></span>](../../../csharp/programming-guide/file-system/index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
