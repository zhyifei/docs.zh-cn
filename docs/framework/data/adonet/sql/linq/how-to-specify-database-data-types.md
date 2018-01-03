---
title: "如何：指定数据库数据类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 60f07a629c981eb0ad72f7c3e2d8537d5ca77515
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="5ef7e-102">如何：指定数据库数据类型</span><span class="sxs-lookup"><span data-stu-id="5ef7e-102">How to: Specify Database Data Types</span></span>
<span data-ttu-id="5ef7e-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>属性<xref:System.Data.Linq.Mapping.ColumnAttribute>特性来指定定义 T-SQL 表声明中的列的确切文本。</span><span class="sxs-lookup"><span data-stu-id="5ef7e-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="5ef7e-104">仅当您打算使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 来创建数据库实例时，才必须指定 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="5ef7e-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="5ef7e-105">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>。</span><span class="sxs-lookup"><span data-stu-id="5ef7e-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="5ef7e-106">指定用于定义 T-SQL 表中数据类型的文本</span><span class="sxs-lookup"><span data-stu-id="5ef7e-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1.  <span data-ttu-id="5ef7e-107">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="5ef7e-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="5ef7e-108">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 属性的值设置为 T-SQL 使用的确切文本。</span><span class="sxs-lookup"><span data-stu-id="5ef7e-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef7e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ef7e-109">See Also</span></span>  
 [<span data-ttu-id="5ef7e-110">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="5ef7e-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="5ef7e-111">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="5ef7e-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
