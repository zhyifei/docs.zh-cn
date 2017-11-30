---
title: "如何：枚举目录和文件"
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
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="e826d-102">如何：枚举目录和文件</span><span class="sxs-lookup"><span data-stu-id="e826d-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="e826d-103">通过使用可返回目录和文件名的可枚举字符串集合的方法，可枚举目录和文件。</span><span class="sxs-lookup"><span data-stu-id="e826d-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="e826d-104">你还可以使用返回的可枚举集合的方法<xref:System.IO.DirectoryInfo>， <xref:System.IO.FileInfo>，或<xref:System.IO.FileSystemInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="e826d-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="e826d-105">在处理目录和文件的大型集合时，可枚举的集合能够比数组提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="e826d-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="e826d-106">您可以使用这些方法从获取的可枚举集合来提供<xref:System.Collections.Generic.IEnumerable%601>参数构造函数的集合类，如<xref:System.Collections.Generic.List%601>类。</span><span class="sxs-lookup"><span data-stu-id="e826d-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="e826d-107">如果你想要获取仅目录或文件的名称，使用的枚举方法<xref:System.IO.Directory>类。</span><span class="sxs-lookup"><span data-stu-id="e826d-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="e826d-108">如果你想要获取目录或文件的其他属性，使用<xref:System.IO.DirectoryInfo>和<xref:System.IO.FileSystemInfo>类。</span><span class="sxs-lookup"><span data-stu-id="e826d-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="e826d-109">下表提供了返回可枚举集合的方法的指南。</span><span class="sxs-lookup"><span data-stu-id="e826d-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="e826d-110">若要枚举</span><span class="sxs-lookup"><span data-stu-id="e826d-110">To enumerate</span></span>|<span data-ttu-id="e826d-111">要返回的可枚举集合</span><span class="sxs-lookup"><span data-stu-id="e826d-111">Enumerable collection to return</span></span>|<span data-ttu-id="e826d-112">要使用的方法</span><span class="sxs-lookup"><span data-stu-id="e826d-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="e826d-113">目录</span><span class="sxs-lookup"><span data-stu-id="e826d-113">Directories</span></span>|<span data-ttu-id="e826d-114">目录名称</span><span class="sxs-lookup"><span data-stu-id="e826d-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="e826d-115">目录信息 (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="e826d-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e826d-116">文件</span><span class="sxs-lookup"><span data-stu-id="e826d-116">Files</span></span>|<span data-ttu-id="e826d-117">文件名</span><span class="sxs-lookup"><span data-stu-id="e826d-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="e826d-118">文件信息 (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="e826d-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e826d-119">文件系统信息</span><span class="sxs-lookup"><span data-stu-id="e826d-119">File system information</span></span>|<span data-ttu-id="e826d-120">文件系统项</span><span class="sxs-lookup"><span data-stu-id="e826d-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="e826d-121">文件系统信息 (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="e826d-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="e826d-122">虽然可以使用 <xref:System.IO.SearchOption.AllDirectories> 枚举提供的 <xref:System.IO.SearchOption> 搜索选项迅速枚举父目录的子目录中的所有文件，但未经授权的访问异常 (<xref:System.UnauthorizedAccessException>) 可能会导致枚举不完整。</span><span class="sxs-lookup"><span data-stu-id="e826d-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="e826d-123">如果可能，这些例外是，你可以捕获它们并继续通过首先枚举目录，然后枚举文件。</span><span class="sxs-lookup"><span data-stu-id="e826d-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="e826d-124">若要枚举目录名称</span><span class="sxs-lookup"><span data-stu-id="e826d-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="e826d-125">使用<xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>方法来获取指定路径中的顶级目录名称的列表。</span><span class="sxs-lookup"><span data-stu-id="e826d-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="e826d-126">枚举目录和子目录中的文件名</span><span class="sxs-lookup"><span data-stu-id="e826d-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="e826d-127">使用 <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 方法可搜索目录及其子目录（可选），并获取与指定搜索模式匹配的文件名称的列表。</span><span class="sxs-lookup"><span data-stu-id="e826d-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="e826d-128">若要枚举的 DirectoryInfo 对象的集合</span><span class="sxs-lookup"><span data-stu-id="e826d-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="e826d-129">使用<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>方法来获取顶级目录的集合。</span><span class="sxs-lookup"><span data-stu-id="e826d-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="e826d-130">若要枚举的所有目录中的 FileInfo 对象的集合</span><span class="sxs-lookup"><span data-stu-id="e826d-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="e826d-131">使用<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>方法来获取与所有目录中指定的搜索模式匹配的文件的集合。</span><span class="sxs-lookup"><span data-stu-id="e826d-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="e826d-132">本示例首先枚举顶级目录以捕获可能的未经授权的访问异常，然后枚举文件。</span><span class="sxs-lookup"><span data-stu-id="e826d-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e826d-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e826d-133">See Also</span></span>  
 [<span data-ttu-id="e826d-134">文件和流 I-O</span><span class="sxs-lookup"><span data-stu-id="e826d-134">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
