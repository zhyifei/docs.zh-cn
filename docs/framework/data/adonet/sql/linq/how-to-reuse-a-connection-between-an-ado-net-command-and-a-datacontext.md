---
title: 如何：重复使用 ADO.NET 命令和 DataContext 之间的连接
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 079b4b28a613ce6a9ae525514b89ea9e316a7c66
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613670"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="0b3fa-102">如何：重复使用 ADO.NET 命令和 DataContext 之间的连接</span><span class="sxs-lookup"><span data-stu-id="0b3fa-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="0b3fa-103">因为[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]一部分[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]系列技术和基于提供的服务[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]，可以重复使用之间的连接[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]命令和一个<xref:System.Data.Linq.DataContext>。</span><span class="sxs-lookup"><span data-stu-id="0b3fa-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b3fa-104">示例</span><span class="sxs-lookup"><span data-stu-id="0b3fa-104">Example</span></span>  
 <span data-ttu-id="0b3fa-105">下面的代码说明了如何重用 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 命令和 <xref:System.Data.Linq.DataContext> 之间的同一连接。</span><span class="sxs-lookup"><span data-stu-id="0b3fa-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="0b3fa-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b3fa-106">See also</span></span>
- [<span data-ttu-id="0b3fa-107">背景信息</span><span class="sxs-lookup"><span data-stu-id="0b3fa-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="0b3fa-108">ADO.NET 和 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0b3fa-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="0b3fa-109">与数据库通信</span><span class="sxs-lookup"><span data-stu-id="0b3fa-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
