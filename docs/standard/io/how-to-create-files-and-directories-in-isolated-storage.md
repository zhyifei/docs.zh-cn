---
title: "如何：在独立存储中创建文件和目录"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="cee9a-102">如何：在独立存储中创建文件和目录</span><span class="sxs-lookup"><span data-stu-id="cee9a-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="cee9a-103">获得独立存储区之后，您可以创建用于存储数据的目录和文件。</span><span class="sxs-lookup"><span data-stu-id="cee9a-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="cee9a-104">在存储区中，则将文件和目录名称指定相对于根目录的虚拟文件系统。</span><span class="sxs-lookup"><span data-stu-id="cee9a-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="cee9a-105">若要创建目录，请使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> 实例方法。</span><span class="sxs-lookup"><span data-stu-id="cee9a-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="cee9a-106">如果您为不存在的目录指定了一个子目录，则会同时创建这两个目录。</span><span class="sxs-lookup"><span data-stu-id="cee9a-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="cee9a-107">如果您指定的目录已存在，该方法将返回而不创建目录，并且不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="cee9a-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="cee9a-108">但是，如果您指定的目录名称包含无效字符，将引发 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 异常。</span><span class="sxs-lookup"><span data-stu-id="cee9a-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="cee9a-109">若要创建文件，请使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="cee9a-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="cee9a-110">在 Windows 操作系统，独立存储文件和目录名不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cee9a-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="cee9a-111">这样，如果您创建了一个名为 `ThisFile.txt` 的文件，然后又创建了名为 `THISFILE.TXT` 的另一个文件，实际上只创建了一个文件。</span><span class="sxs-lookup"><span data-stu-id="cee9a-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="cee9a-112">文件名称将保留其原始的大小写，用于显示目的。</span><span class="sxs-lookup"><span data-stu-id="cee9a-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cee9a-113">示例</span><span class="sxs-lookup"><span data-stu-id="cee9a-113">Example</span></span>  
 <span data-ttu-id="cee9a-114">下面的代码示例说明了如何在独立存储区中创建文件和目录。</span><span class="sxs-lookup"><span data-stu-id="cee9a-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cee9a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cee9a-115">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [<span data-ttu-id="cee9a-116">独立存储</span><span class="sxs-lookup"><span data-stu-id="cee9a-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
