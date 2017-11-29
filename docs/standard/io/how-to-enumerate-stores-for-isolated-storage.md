---
title: "如何：枚举独立存储的存储区"
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
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f8863f1d8b3c7f4ed8f65f8f8eb3e8af51b0405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a><span data-ttu-id="6f656-102">如何：枚举独立存储的存储区</span><span class="sxs-lookup"><span data-stu-id="6f656-102">How to: Enumerate Stores for Isolated Storage</span></span>
<span data-ttu-id="6f656-103">您可以使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> 静态方法枚举当前用户的所有独立存储区。</span><span class="sxs-lookup"><span data-stu-id="6f656-103">You can enumerate all isolated stores for the current user by using the  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> static method.</span></span> <span data-ttu-id="6f656-104">该方法采用 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 值并且返回 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 枚举器。</span><span class="sxs-lookup"><span data-stu-id="6f656-104">This  method takes an <xref:System.IO.IsolatedStorage.IsolatedStorageScope> value and returns an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> enumerator.</span></span> <span data-ttu-id="6f656-105">若要枚举存储区，您必须具有指定<xref:System.Security.Permissions.IsolatedStorageFilePermission> 值的 <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> 权限。</span><span class="sxs-lookup"><span data-stu-id="6f656-105">To enumerate stores, you must have the <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission that specifies the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span> <span data-ttu-id="6f656-106">如果调用采用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 值的 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> 方法，它将返回一组为当前用户定义的 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 对象。</span><span class="sxs-lookup"><span data-stu-id="6f656-106">If you call the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method with the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> value, it returns an array of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that are defined for the current user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f656-107">示例</span><span class="sxs-lookup"><span data-stu-id="6f656-107">Example</span></span>  
 <span data-ttu-id="6f656-108">下面的代码示例使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 方法获取按用户和程序集隔离的存储区，创建一些文件，并检索这些文件。</span><span class="sxs-lookup"><span data-stu-id="6f656-108">The following code example obtains a store that is isolated by user and assembly, creates a few files, and retrieves those files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6f656-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f656-109">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="6f656-110">独立存储</span><span class="sxs-lookup"><span data-stu-id="6f656-110">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
