---
title: 如何：将列表示为时间戳列或版本列
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: 2fc8aaf260dc3657e33e539939fdf58ad8224c93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361234"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="943ec-102">如何：将列表示为时间戳列或版本列</span><span class="sxs-lookup"><span data-stu-id="943ec-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="943ec-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>属性<xref:System.Data.Linq.Mapping.ColumnAttribute>属性将字段或属性指定为表示保存数据库时间戳或版本号的数字的数据库列。</span><span class="sxs-lookup"><span data-stu-id="943ec-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="943ec-104">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="943ec-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="943ec-105">将字段或属性指定为表示时间戳列或版本列</span><span class="sxs-lookup"><span data-stu-id="943ec-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1.  <span data-ttu-id="943ec-106">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="943ec-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="943ec-107">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 属性值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="943ec-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943ec-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="943ec-108">See Also</span></span>  
 [<span data-ttu-id="943ec-109">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="943ec-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="943ec-110">如何：指定针对并发冲突对哪些成员进行测试</span><span class="sxs-lookup"><span data-stu-id="943ec-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 [<span data-ttu-id="943ec-111">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="943ec-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
