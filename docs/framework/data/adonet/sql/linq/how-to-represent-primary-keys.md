---
title: 如何：表示主键
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 28c62798f965edfcffe1a156213c2481a8193b49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943533"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="6b40a-102">如何：表示主键</span><span class="sxs-lookup"><span data-stu-id="6b40a-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="6b40a-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 特性<xref:System.Data.Linq.Mapping.ColumnAttribute>上的<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>属性可以指定一个属性或字段来表示数据库列的主键。</span><span class="sxs-lookup"><span data-stu-id="6b40a-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="6b40a-104">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="6b40a-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6b40a-105">不支持作为主键的计算所得列。</span><span class="sxs-lookup"><span data-stu-id="6b40a-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="6b40a-106">将属性或字段指定为主键</span><span class="sxs-lookup"><span data-stu-id="6b40a-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="6b40a-107">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="6b40a-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="6b40a-108">将其值指定为 `true`。</span><span class="sxs-lookup"><span data-stu-id="6b40a-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b40a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b40a-109">See also</span></span>

- [<span data-ttu-id="6b40a-110">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="6b40a-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="6b40a-111">如何：使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="6b40a-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
