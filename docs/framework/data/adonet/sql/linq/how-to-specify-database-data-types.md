---
title: 如何：指定数据库数据类型
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 67f23ff06aefbcff4ba7e2eaab63d9b8493b9717
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333205"
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="fb13a-102">如何：指定数据库数据类型</span><span class="sxs-lookup"><span data-stu-id="fb13a-102">How to: Specify Database Data Types</span></span>
<span data-ttu-id="fb13a-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>属性上的<xref:System.Data.Linq.Mapping.ColumnAttribute>属性指定定义 T-SQL 表声明中的列的确切文本。</span><span class="sxs-lookup"><span data-stu-id="fb13a-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="fb13a-104">仅当您打算使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 来创建数据库实例时，才必须指定 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="fb13a-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="fb13a-105">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>。</span><span class="sxs-lookup"><span data-stu-id="fb13a-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="fb13a-106">指定用于定义 T-SQL 表中数据类型的文本</span><span class="sxs-lookup"><span data-stu-id="fb13a-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1. <span data-ttu-id="fb13a-107">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="fb13a-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="fb13a-108">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 属性的值设置为 T-SQL 使用的确切文本。</span><span class="sxs-lookup"><span data-stu-id="fb13a-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb13a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb13a-109">See also</span></span>

- [<span data-ttu-id="fb13a-110">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="fb13a-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="fb13a-111">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="fb13a-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
