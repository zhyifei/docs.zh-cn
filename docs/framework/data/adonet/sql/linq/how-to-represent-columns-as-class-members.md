---
title: 如何：将列表示为类成员
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 009da2579a6fe15cea3913ae5844fc886da2586c
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910747"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="34555-102">如何：将列表示为类成员</span><span class="sxs-lookup"><span data-stu-id="34555-102">How to: Represent Columns as Class Members</span></span>
<span data-ttu-id="34555-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute>属性来将字段或属性与数据库列相关联。</span><span class="sxs-lookup"><span data-stu-id="34555-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="34555-104">将字段或属性映射到数据库列</span><span class="sxs-lookup"><span data-stu-id="34555-104">To map a field or property to a database column</span></span>  
  
- <span data-ttu-id="34555-105">将 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute) 添加到相应属性 (Property) 或字段的声明中。</span><span class="sxs-lookup"><span data-stu-id="34555-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34555-106">示例</span><span class="sxs-lookup"><span data-stu-id="34555-106">Example</span></span>  
 <span data-ttu-id="34555-107">下面的代码将 `CustomerID` 类中的 `Customer` 字段映射到 `CustomerID` 数据库表中的 `Customers` 列。</span><span class="sxs-lookup"><span data-stu-id="34555-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="34555-108">如果可以推断出名称，您无需指定 <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="34555-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="34555-109">如果您未指定名称，则假定此名称与此属性或字段的名称相同。</span><span class="sxs-lookup"><span data-stu-id="34555-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34555-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="34555-110">See also</span></span>

- [<span data-ttu-id="34555-111">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="34555-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="34555-112">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="34555-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
