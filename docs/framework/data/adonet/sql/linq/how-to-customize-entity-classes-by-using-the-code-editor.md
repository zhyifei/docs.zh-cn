---
title: 如何：通过使用代码编辑器自定义实体类
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 58544441ec722e5cf0e18c113bbce0bbf40b92bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360486"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="f4458-102">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="f4458-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="f4458-103">使用 Visual Studio 的开发人员可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]若要创建或自定义它们的实体类。</span><span class="sxs-lookup"><span data-stu-id="f4458-103">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="f4458-104">你还可以使用 Visual Studio 代码编辑器编写你自己的映射代码或自定义已生成的代码。</span><span class="sxs-lookup"><span data-stu-id="f4458-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="f4458-105">有关详细信息，请参阅[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="f4458-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="f4458-106">本节中的主题说明如何自定义对象模型。</span><span class="sxs-lookup"><span data-stu-id="f4458-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="f4458-107">如何：指定数据库名称</span><span class="sxs-lookup"><span data-stu-id="f4458-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="f4458-108">描述如何使用 <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="f4458-109">如何：将表表示为类</span><span class="sxs-lookup"><span data-stu-id="f4458-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="f4458-110">描述如何使用 <xref:System.Data.Linq.Mapping.TableAttribute>。</span><span class="sxs-lookup"><span data-stu-id="f4458-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="f4458-111">如何：将列表示为类成员</span><span class="sxs-lookup"><span data-stu-id="f4458-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="f4458-112">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute>。</span><span class="sxs-lookup"><span data-stu-id="f4458-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="f4458-113">如何：表示主键</span><span class="sxs-lookup"><span data-stu-id="f4458-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="f4458-114">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="f4458-115">如何：映射数据库关系</span><span class="sxs-lookup"><span data-stu-id="f4458-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="f4458-116">提供使用 <xref:System.Data.Linq.Mapping.AssociationAttribute> 属性的示例。</span><span class="sxs-lookup"><span data-stu-id="f4458-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="f4458-117">如何：将列表示为数据库生成的</span><span class="sxs-lookup"><span data-stu-id="f4458-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="f4458-118">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="f4458-119">如何：将列表示为时间戳列或版本列</span><span class="sxs-lookup"><span data-stu-id="f4458-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="f4458-120">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="f4458-121">如何：指定数据库数据类型</span><span class="sxs-lookup"><span data-stu-id="f4458-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="f4458-122">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="f4458-123">如何：表示计算所得的列</span><span class="sxs-lookup"><span data-stu-id="f4458-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="f4458-124">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="f4458-125">如何：指定专用存储字段</span><span class="sxs-lookup"><span data-stu-id="f4458-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="f4458-126">描述如何使用 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="f4458-127">如何：将列表示为允许 Null 值</span><span class="sxs-lookup"><span data-stu-id="f4458-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="f4458-128">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="f4458-129">如何：映射继承层次结构</span><span class="sxs-lookup"><span data-stu-id="f4458-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="f4458-130">说明指定继承层次结构所需的映射。</span><span class="sxs-lookup"><span data-stu-id="f4458-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="f4458-131">如何：指定并发冲突检查</span><span class="sxs-lookup"><span data-stu-id="f4458-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="f4458-132">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4458-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4458-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4458-133">See Also</span></span>  
 [<span data-ttu-id="f4458-134">SqlMetal.exe（代码生成工具）</span><span class="sxs-lookup"><span data-stu-id="f4458-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
