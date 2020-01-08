---
title: 文件系统和注册表 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 3e78d49881a4def5fe9c70ecfe890c8ffee811e8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635296"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="0d486-102">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="0d486-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="0d486-103">下面各主题介绍了如何使用 C# 和 .NET Framework 对文件、文件夹和注册表执行各种基本操作。</span><span class="sxs-lookup"><span data-stu-id="0d486-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d486-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="0d486-104">In This Section</span></span>  
  
|<span data-ttu-id="0d486-105">**标题**</span><span class="sxs-lookup"><span data-stu-id="0d486-105">**Title**</span></span>|<span data-ttu-id="0d486-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="0d486-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="0d486-107">如何循环访问目录树</span><span class="sxs-lookup"><span data-stu-id="0d486-107">How to iterate through a directory tree</span></span>](./how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="0d486-108">介绍了如何手动循环访问目录树。</span><span class="sxs-lookup"><span data-stu-id="0d486-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="0d486-109">如何获取有关文件、文件夹和驱动器的信息</span><span class="sxs-lookup"><span data-stu-id="0d486-109">How to get information about files, folders, and drives</span></span>](./how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="0d486-110">介绍了如何检索有关文件、文件夹和驱动器的信息，如创建时间和大小。</span><span class="sxs-lookup"><span data-stu-id="0d486-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="0d486-111">如何创建文件或文件夹</span><span class="sxs-lookup"><span data-stu-id="0d486-111">How to create a file or folder</span></span>](./how-to-create-a-file-or-folder.md)|<span data-ttu-id="0d486-112">介绍了如何新建文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d486-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="0d486-113">如何复制、删除和移动文件和文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="0d486-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="0d486-114">介绍了如何复制、删除、移动文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d486-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="0d486-115">如何提供文件操作进度对话框</span><span class="sxs-lookup"><span data-stu-id="0d486-115">How to provide a progress dialog box for file operations</span></span>](./how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="0d486-116">介绍了如何显示特定文件操作的标准 Windows 进度对话框。</span><span class="sxs-lookup"><span data-stu-id="0d486-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="0d486-117">如何写入文本文件</span><span class="sxs-lookup"><span data-stu-id="0d486-117">How to write to a text file</span></span>](./how-to-write-to-a-text-file.md)|<span data-ttu-id="0d486-118">介绍了如何将内容写入文本文件。</span><span class="sxs-lookup"><span data-stu-id="0d486-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="0d486-119">如何读取文本文件中的内容</span><span class="sxs-lookup"><span data-stu-id="0d486-119">How to read from a text file</span></span>](./how-to-read-from-a-text-file.md)|<span data-ttu-id="0d486-120">介绍了如何读取文本文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="0d486-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="0d486-121">如何一次一行地读取文本文件</span><span class="sxs-lookup"><span data-stu-id="0d486-121">How to read a text file one line at a time</span></span>](./how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="0d486-122">介绍了如何一次一行地检索文件文本。</span><span class="sxs-lookup"><span data-stu-id="0d486-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="0d486-123">如何在注册表中创建注册表项</span><span class="sxs-lookup"><span data-stu-id="0d486-123">How to create a key in the registry</span></span>](./how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="0d486-124">介绍了如何将注册表项写入系统注册表。</span><span class="sxs-lookup"><span data-stu-id="0d486-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="0d486-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="0d486-125">Related Sections</span></span>  
 [<span data-ttu-id="0d486-126">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="0d486-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="0d486-127">如何复制、删除和移动文件和文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="0d486-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)
  
 [<span data-ttu-id="0d486-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0d486-128">C# Programming Guide</span></span>](../index.md)  
  
 [<span data-ttu-id="0d486-129">文件、文件夹和驱动器</span><span class="sxs-lookup"><span data-stu-id="0d486-129">Files, Folders and Drives</span></span>](./index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
