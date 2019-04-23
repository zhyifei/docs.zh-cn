---
title: 如何：表示计算所得的列
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: df72562b303e5b9a7c31334df06926f157b59b05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324730"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="4b707-102">如何：表示计算所得的列</span><span class="sxs-lookup"><span data-stu-id="4b707-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="4b707-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>属性上的<xref:System.Data.Linq.Mapping.ColumnAttribute>属性，以表示其内容是计算的结果的列。</span><span class="sxs-lookup"><span data-stu-id="4b707-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="4b707-104">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>。</span><span class="sxs-lookup"><span data-stu-id="4b707-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4b707-105">不支持作为主键的计算所得列。</span><span class="sxs-lookup"><span data-stu-id="4b707-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="4b707-106">表示计算所得的列</span><span class="sxs-lookup"><span data-stu-id="4b707-106">To represent a computed column</span></span>  
  
1. <span data-ttu-id="4b707-107">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="4b707-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="4b707-108">将公式的字符串表示形式赋给 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="4b707-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b707-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b707-109">See also</span></span>

- [<span data-ttu-id="4b707-110">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="4b707-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="4b707-111">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="4b707-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
