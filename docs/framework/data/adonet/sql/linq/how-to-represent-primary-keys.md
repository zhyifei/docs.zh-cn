---
title: "如何：表示主键"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: cf1ba7d0f08d6b0a7dc37af233ad27695cde2a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="66626-102">如何：表示主键</span><span class="sxs-lookup"><span data-stu-id="66626-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="66626-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>属性<xref:System.Data.Linq.Mapping.ColumnAttribute>属性可指定属性或字段来表示数据库列的主键。</span><span class="sxs-lookup"><span data-stu-id="66626-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="66626-104">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="66626-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="66626-105"> 不支持作为主键的计算所得列。</span><span class="sxs-lookup"><span data-stu-id="66626-105"> does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="66626-106">将属性或字段指定为主键</span><span class="sxs-lookup"><span data-stu-id="66626-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="66626-107">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="66626-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="66626-108">将其值指定为 `true`。</span><span class="sxs-lookup"><span data-stu-id="66626-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66626-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="66626-109">See Also</span></span>  
 [<span data-ttu-id="66626-110">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="66626-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="66626-111">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="66626-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
