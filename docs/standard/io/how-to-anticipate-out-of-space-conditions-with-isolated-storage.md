---
title: "如何：预见独立存储中的空间不足条件"
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
- data stores, quotas
- isolated storage, quotas
- quanitity of isolated storage used
- limit on isolated storage used
- stores, quotas
- stores, out of space conditions
- data storage using isolated storage, quotas
- storing data using isolated storage, quotas
- space remaining in isolated storage
- data stores, out of space conditions
- storing data using isolated storage, out of space conditions
- quotas for isolated storage
- isolated storage, out of space conditions
- data storage using isolated storage, out of space conditions
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d813522d0aeb9bf37582c167760d44268df27039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>如何：预见独立存储中的空间不足条件
使用独立的存储的代码受限制，[配额](../../../docs/standard/io/isolated-storage.md#quotas)，指定的最大大小为在其中的数据隔离舱独立存储文件和目录存在。 该配额由安全策略定义，管理员可以对其进行配置。 如果尝试写入数据时超过了所允许的最大大小，将引发 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 异常并使操作失败。 这有助于防止恶意拒绝服务攻击可能导致应用程序拒绝请求，因为数据存储被填满。  
  
 若要帮助你确定是否有可能无法为此，给定的写入尝试<xref:System.IO.IsolatedStorage.IsolatedStorage>类提供了三个只读属性： <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>， <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>，和<xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>。 您可以使用这些属性来确定写入存储区是否将导致超过存储区所允许的最大大小。 记住独立存储可能被同时访问；因此，当计算剩余存储量时，该存储空间可能在您尝试写入存储区时已被使用。 但是，您可以使用存储区的最大大小来确定是否将达到可用存储的上限。  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> 属性依赖程序集中的证据来正常工作。 因此，只应在使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>、<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> 或 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 方法创建的 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 对象上检索此属性。 以其他任何方式创建的 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 对象（例如从 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 方法返回的对象）将无法返回准确的最大大小。  
  
## <a name="example"></a>示例  
 下面的代码示例获取独立存储区，创建一些文件，并检索<xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>属性。 以字节为单位报告剩余的空间。  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [独立存储](../../../docs/standard/io/isolated-storage.md)  
 [如何：获取独立存储的存储区](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
