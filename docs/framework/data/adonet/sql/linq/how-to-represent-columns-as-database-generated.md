---
title: 如何：将列表示为数据库生成的
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 2fca0c2fb1d28b5e83902f8664d1c7331774718b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148247"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="64853-102">如何：将列表示为数据库生成的</span><span class="sxs-lookup"><span data-stu-id="64853-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="64853-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>属性上的<xref:System.Data.Linq.Mapping.ColumnAttribute>属性可指定字段或属性表示数据库生成的列。</span><span class="sxs-lookup"><span data-stu-id="64853-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="64853-104">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>。</span><span class="sxs-lookup"><span data-stu-id="64853-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="64853-105">指定字段或属性表示数据库生成的列</span><span class="sxs-lookup"><span data-stu-id="64853-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="64853-106">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="64853-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="64853-107">将此属性 (Property) 的值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="64853-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64853-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="64853-108">See also</span></span>

- [<span data-ttu-id="64853-109">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="64853-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="64853-110">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="64853-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
