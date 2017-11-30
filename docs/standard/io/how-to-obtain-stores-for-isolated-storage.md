---
title: "如何：获取独立存储的存储区"
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
- cpp
helpviewer_keywords:
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb0b877aa0f4cee36bd1f8c1cea624cf9368fbaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>如何：获取独立存储的存储区
独立存储区公开数据隔离舱中的虚拟文件系统。 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 类提供许多与独立存储区交互的方法。 为了创建和检索存储区，<xref:System.IO.IsolatedStorage.IsolatedStorageFile> 提供了三种静态方法：  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> 返回按用户和程序集隔离的存储。  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 返回按域和程序集隔离的存储。  
  
     这两种方法检索属于所调用代码的存储区。  
  
-   静态方法<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>返回指定作用域参数的组合中传递的独立存储区。  
  
 下面的示例返回按用户、程序集和域隔离的存储区。  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 您可以使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法指定存储区应该和漫游用户配置文件一起漫游。 有关如何对此进行设置的详细信息，请参阅[类型的隔离](../../../docs/standard/io/types-of-isolation.md)。  
  
 默认情况下，不同的存储区是通过在不同的程序集内的独立存储区。 通过在 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法的参数中传递程序集或域证据，可以访问不同程序集或域的存储区。 这要求通过应用程序域标识来访问独立的存储的权限。 有关详细信息，请参阅 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法重载。  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>、<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 和 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 方法返回 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 对象。 若要帮助您决定哪种隔离类型在最适合于你的情况，请参阅[类型的隔离](../../../docs/standard/io/types-of-isolation.md)。 当您具有了独立存储文件对象时，您便可以使用独立存储方法来读取、写入、创建和删除文件及目录了。  
  
 没有一种机制可用来防止代码向没有足够访问权限来自己获取存储区的代码传递 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 对象。 对的引用时只检查域和程序集的标识和独立的存储权限<xref:System.IO.IsolatedStorage.IsolatedStorage>获取对象，通常在<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>， <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>，或<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>方法。 保护对引用<xref:System.IO.IsolatedStorage.IsolatedStorageFile>对象负责，因此，使用这些引用的代码。  
  
## <a name="example"></a>示例  
 下面的代码提供了一个简单的类示例，它包含按用户和程序集隔离的存储区。 通过向 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> 方法传递的参数添加 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>，此代码可更改为检索按用户、域和程序集隔离的存储区。  
  
 运行代码后，您可以确认通过键入已创建了存储区**StoreAdm /LIST**在命令行。 这将在运行[独立存储工具 (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)并列出所有当前隔离存储消息以供用户。  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [独立存储](../../../docs/standard/io/isolated-storage.md)  
 [隔离的类型](../../../docs/standard/io/types-of-isolation.md)  
 [Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）
