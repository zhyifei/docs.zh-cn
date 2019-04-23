---
title: 如何：通过使用代码编辑器自定义实体类
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 05a523f8b98c7b64350b67c217baba07dca14de3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155163"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="17257-102">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="17257-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="17257-103">使用 Visual Studio 的开发人员可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]创建或自定义其实体类。</span><span class="sxs-lookup"><span data-stu-id="17257-103">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="17257-104">若要编写您自己的映射代码或自定义已生成的代码，还可以使用 Visual Studio 代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="17257-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="17257-105">有关详细信息，请参阅[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="17257-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="17257-106">本节中的主题说明如何自定义对象模型。</span><span class="sxs-lookup"><span data-stu-id="17257-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="17257-107">如何：指定数据库名称</span><span class="sxs-lookup"><span data-stu-id="17257-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="17257-108">描述如何使用 <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="17257-109">如何：表表示为类</span><span class="sxs-lookup"><span data-stu-id="17257-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="17257-110">描述如何使用 <xref:System.Data.Linq.Mapping.TableAttribute>。</span><span class="sxs-lookup"><span data-stu-id="17257-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="17257-111">如何：列表示为类成员</span><span class="sxs-lookup"><span data-stu-id="17257-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="17257-112">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute>。</span><span class="sxs-lookup"><span data-stu-id="17257-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="17257-113">如何：表示主键</span><span class="sxs-lookup"><span data-stu-id="17257-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="17257-114">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="17257-115">如何：映射数据库关系</span><span class="sxs-lookup"><span data-stu-id="17257-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="17257-116">提供使用 <xref:System.Data.Linq.Mapping.AssociationAttribute> 属性的示例。</span><span class="sxs-lookup"><span data-stu-id="17257-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="17257-117">如何：列表示为数据库生成</span><span class="sxs-lookup"><span data-stu-id="17257-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="17257-118">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="17257-119">如何：表示为时间戳列或版本列</span><span class="sxs-lookup"><span data-stu-id="17257-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="17257-120">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="17257-121">如何：指定数据库数据类型</span><span class="sxs-lookup"><span data-stu-id="17257-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="17257-122">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="17257-123">如何：表示计算所得的列</span><span class="sxs-lookup"><span data-stu-id="17257-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="17257-124">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="17257-125">如何：指定专用存储字段</span><span class="sxs-lookup"><span data-stu-id="17257-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="17257-126">描述如何使用 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="17257-127">如何：列表示为允许 Null 值</span><span class="sxs-lookup"><span data-stu-id="17257-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="17257-128">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="17257-129">如何：映射继承层次结构</span><span class="sxs-lookup"><span data-stu-id="17257-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="17257-130">说明指定继承层次结构所需的映射。</span><span class="sxs-lookup"><span data-stu-id="17257-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="17257-131">如何：指定并发冲突检查</span><span class="sxs-lookup"><span data-stu-id="17257-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="17257-132">描述如何使用 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>。</span><span class="sxs-lookup"><span data-stu-id="17257-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17257-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="17257-133">See also</span></span>

- [<span data-ttu-id="17257-134">SqlMetal.exe（代码生成工具）</span><span class="sxs-lookup"><span data-stu-id="17257-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
