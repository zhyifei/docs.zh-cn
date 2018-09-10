---
title: 如何：获取独立存储的存储区
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e2f87bfe1e3e7f3a1c8135c047b25a998793453
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084065"
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a><span data-ttu-id="f8cb6-102">如何：获取独立存储的存储区</span><span class="sxs-lookup"><span data-stu-id="f8cb6-102">How to: Obtain Stores for Isolated Storage</span></span>
<span data-ttu-id="f8cb6-103">独立存储区公开数据隔离舱中的虚拟文件系统。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-103">An isolated store exposes a virtual file system within a data compartment.</span></span> <span data-ttu-id="f8cb6-104"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> 类提供许多与独立存储区交互的方法。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-104">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies a number of methods for interacting with an isolated store.</span></span> <span data-ttu-id="f8cb6-105">为了创建和检索存储区，<xref:System.IO.IsolatedStorage.IsolatedStorageFile> 提供了三种静态方法：</span><span class="sxs-lookup"><span data-stu-id="f8cb6-105">To create and retrieve stores, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> provides three static methods:</span></span>  
  
-   <span data-ttu-id="f8cb6-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> 返回按用户和程序集隔离的存储。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> returns storage that is isolated by user and assembly.</span></span>  
  
-   <span data-ttu-id="f8cb6-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 返回按域和程序集隔离的存储。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> returns storage that is isolated by domain and assembly.</span></span>  
  
     <span data-ttu-id="f8cb6-108">这两种方法检索属于所调用代码的存储区。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-108">Both methods retrieve a store that belongs to the code from which they are called.</span></span>  
  
-   <span data-ttu-id="f8cb6-109">静态方法 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 返回通过传入一组范围参数指定的独立存储。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-109">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> returns an isolated store that is specified by passing in a combination of scope parameters.</span></span>  
  
 <span data-ttu-id="f8cb6-110">下面的示例返回按用户、程序集和域隔离的存储区。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-110">The following code returns a store that is isolated by user, assembly, and domain.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 <span data-ttu-id="f8cb6-111">您可以使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法指定存储区应该和漫游用户配置文件一起漫游。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-111">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method to specify that a store should roam with a roaming user profile.</span></span> <span data-ttu-id="f8cb6-112">若要详细了解如何对此进行设置，请参阅[隔离类型](../../../docs/standard/io/types-of-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-112">For details on how to set this up, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span>  
  
 <span data-ttu-id="f8cb6-113">从不同程序集获取的独立存储默认就是不同的存储。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-113">Isolated stores obtained from within different assemblies are, by default, different stores.</span></span> <span data-ttu-id="f8cb6-114">通过在 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法的参数中传递程序集或域证据，可以访问不同程序集或域的存储区。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-114">You can access the store of a different assembly or domain by passing in the assembly or domain evidence in the parameters of the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="f8cb6-115">这需要拥有权限，才能按应用域标识访问独立存储。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-115">This requires permission to access isolated storage by application domain identity.</span></span> <span data-ttu-id="f8cb6-116">有关详细信息，请参阅 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法重载。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-116">For more information, see the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method overloads.</span></span>  
  
 <span data-ttu-id="f8cb6-117"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>、<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 和 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法返回 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 对象。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-117">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> methods return an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object.</span></span> <span data-ttu-id="f8cb6-118">若要了解如何确定哪种隔离类型最适合自己的情况，请参阅[隔离类型](../../../docs/standard/io/types-of-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-118">To help you decide which isolation type is most appropriate for your situation, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span> <span data-ttu-id="f8cb6-119">当您具有了独立存储文件对象时，您便可以使用独立存储方法来读取、写入、创建和删除文件及目录了。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-119">When you have an isolated storage file object, you can use the isolated storage methods to read, write, create, and delete files and directories.</span></span>  
  
 <span data-ttu-id="f8cb6-120">没有一种机制可用来防止代码向没有足够访问权限来自己获取存储区的代码传递 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 对象。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-120">There is no mechanism that prevents code from passing an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object to code that does not have sufficient access to get the store itself.</span></span> <span data-ttu-id="f8cb6-121">仅当获得对 <xref:System.IO.IsolatedStorage.IsolatedStorage> 对象的引用时（通常在 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>、<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 或 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法中），才会检查域和程序集标识以及独立存储权限。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-121">Domain and assembly identities and isolated storage permissions are checked only when a reference to an <xref:System.IO.IsolatedStorage.IsolatedStorage> object is obtained, typically in the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="f8cb6-122">因此，保护对 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 对象的引用是使用这些引用的代码的责任。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-122">Protecting references to <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects is, therefore, the responsibility of the code that uses these references.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8cb6-123">示例</span><span class="sxs-lookup"><span data-stu-id="f8cb6-123">Example</span></span>  
 <span data-ttu-id="f8cb6-124">下面的代码提供了一个简单的类示例，它包含按用户和程序集隔离的存储区。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-124">The following code provides a simple example of a class obtaining a store that is isolated by user and assembly.</span></span> <span data-ttu-id="f8cb6-125">通过向 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> 方法传递的参数添加 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>，此代码可更改为检索按用户、域和程序集隔离的存储区。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-125">The code can be changed to retrieve a store that is isolated by user, domain, and assembly by adding <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> to the arguments that the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method passes.</span></span>  
  
 <span data-ttu-id="f8cb6-126">运行代码后，可以在命令行处键入“ StoreAdm /LIST”，以确认存储是否已创建。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-126">After you run the code, you can confirm that a store was created by typing **StoreAdm /LIST** at the command line.</span></span> <span data-ttu-id="f8cb6-127">这会运行[独立存储工具 (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)，并列出用户当前的所有独立存储。</span><span class="sxs-lookup"><span data-stu-id="f8cb6-127">This runs the [Isolated Storage tool (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) and lists all the current isolated stores for the user.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="f8cb6-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8cb6-128">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
- [<span data-ttu-id="f8cb6-129">独立存储</span><span class="sxs-lookup"><span data-stu-id="f8cb6-129">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
- [<span data-ttu-id="f8cb6-130">隔离的类型</span><span class="sxs-lookup"><span data-stu-id="f8cb6-130">Types of Isolation</span></span>](../../../docs/standard/io/types-of-isolation.md)  
- <span data-ttu-id="f8cb6-131">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="f8cb6-131">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>
