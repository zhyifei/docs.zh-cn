---
title: 如何：枚举目录和文件
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de83395df9e8c89a92e85b96ddd15e9f0be6ad5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207689"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="6a2ff-102">如何：枚举目录和文件</span><span class="sxs-lookup"><span data-stu-id="6a2ff-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="6a2ff-103">通过使用可返回目录和文件名的可枚举字符串集合的方法，可枚举目录和文件。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="6a2ff-104">也可以使用返回 <xref:System.IO.DirectoryInfo>、<xref:System.IO.FileInfo> 或 <xref:System.IO.FileSystemInfo> 对象的可枚举集合的方法。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="6a2ff-105">在处理目录和文件的大型集合时，可枚举的集合能够比数组提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="6a2ff-106">还可以使用通过这些方法获取的可枚举集合，为集合类（如 <xref:System.Collections.Generic.List%601> 类）的构造函数提供 <xref:System.Collections.Generic.IEnumerable%601> 参数。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="6a2ff-107">如果只想获取目录名称或文件名，请使用 <xref:System.IO.Directory> 类的枚举方法。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="6a2ff-108">若要获取目录或文件的其他属性，请使用 <xref:System.IO.DirectoryInfo> 和 <xref:System.IO.FileSystemInfo> 类。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="6a2ff-109">下表列出了与返回可枚举集合的方法相关的指南。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="6a2ff-110">要枚举的内容</span><span class="sxs-lookup"><span data-stu-id="6a2ff-110">To enumerate</span></span>|<span data-ttu-id="6a2ff-111">要返回的可枚举集合</span><span class="sxs-lookup"><span data-stu-id="6a2ff-111">Enumerable collection to return</span></span>|<span data-ttu-id="6a2ff-112">要使用的方法</span><span class="sxs-lookup"><span data-stu-id="6a2ff-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="6a2ff-113">目录</span><span class="sxs-lookup"><span data-stu-id="6a2ff-113">Directories</span></span>|<span data-ttu-id="6a2ff-114">目录名称</span><span class="sxs-lookup"><span data-stu-id="6a2ff-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="6a2ff-115">目录信息 (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="6a2ff-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6a2ff-116">文件</span><span class="sxs-lookup"><span data-stu-id="6a2ff-116">Files</span></span>|<span data-ttu-id="6a2ff-117">文件名</span><span class="sxs-lookup"><span data-stu-id="6a2ff-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="6a2ff-118">文件信息 (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="6a2ff-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6a2ff-119">文件系统信息</span><span class="sxs-lookup"><span data-stu-id="6a2ff-119">File system information</span></span>|<span data-ttu-id="6a2ff-120">文件系统项</span><span class="sxs-lookup"><span data-stu-id="6a2ff-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="6a2ff-121">文件系统信息 (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="6a2ff-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="6a2ff-122">虽然可以使用 <xref:System.IO.SearchOption.AllDirectories> 枚举提供的 <xref:System.IO.SearchOption> 搜索选项迅速枚举父目录的子目录中的所有文件，但未经授权的访问异常 (<xref:System.UnauthorizedAccessException>) 可能会导致枚举不完整。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="6a2ff-123">如果这些异常可能会抛出，可以捕获它们并继续执行，通过先枚举目录，再枚举文件。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="6a2ff-124">枚举目录名称的具体步骤</span><span class="sxs-lookup"><span data-stu-id="6a2ff-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="6a2ff-125">使用 <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> 方法，获取指定路径中顶级目录名称的列表。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="6a2ff-126">枚举目录和子目录中的文件名</span><span class="sxs-lookup"><span data-stu-id="6a2ff-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="6a2ff-127">使用 <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 方法可搜索目录及其子目录（可选），并获取与指定搜索模式匹配的文件名称的列表。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="6a2ff-128">枚举 DirectoryInfo 对象集合的具体步骤</span><span class="sxs-lookup"><span data-stu-id="6a2ff-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="6a2ff-129">使用 <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> 方法，获取顶级目录的集合。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="6a2ff-130">枚举所有目录中 FileInfo 对象集合的具体步骤</span><span class="sxs-lookup"><span data-stu-id="6a2ff-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="6a2ff-131">使用 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> 方法，获取与所有目录中指定搜索模式匹配的文件集合。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="6a2ff-132">此示例先枚举顶级目录以捕获可能的未授权访问异常，再枚举文件。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6a2ff-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a2ff-133">See also</span></span>

- [<span data-ttu-id="6a2ff-134">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="6a2ff-134">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
