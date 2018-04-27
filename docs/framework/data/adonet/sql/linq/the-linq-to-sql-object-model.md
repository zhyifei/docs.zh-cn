---
title: LINQ to SQL 对象模型
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: cc05166cffdd7254c657f0c490afaaac4cf08fcb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="the-linq-to-sql-object-model"></a><span data-ttu-id="511e8-102">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="511e8-102">The LINQ to SQL Object Model</span></span>
<span data-ttu-id="511e8-103">在[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，用开发人员的编程语言表示的对象模型映射到关系数据库的数据模型。</span><span class="sxs-lookup"><span data-stu-id="511e8-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model expressed in the programming language of the developer is mapped to the data model of a relational database.</span></span> <span data-ttu-id="511e8-104">然后就会按照对象模型来执行对数据的操作。</span><span class="sxs-lookup"><span data-stu-id="511e8-104">Operations on the data are then conducted according to the object model.</span></span>  
  
 <span data-ttu-id="511e8-105">在这种情况下，您无需向数据库发出数据库命令（例如，`INSERT`），</span><span class="sxs-lookup"><span data-stu-id="511e8-105">In this scenario, you do not issue database commands (for example, `INSERT`) to the database.</span></span> <span data-ttu-id="511e8-106">而是在对象模型中更改值和执行方法。</span><span class="sxs-lookup"><span data-stu-id="511e8-106">Instead, you change values and execute methods within your object model.</span></span> <span data-ttu-id="511e8-107">当您需要查询数据库或向其发送更改时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将您的请求转换成正确的 SQL 命令，然后将这些命令发送到数据库。</span><span class="sxs-lookup"><span data-stu-id="511e8-107">When you want to query the database or send it changes, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your requests into the correct SQL commands and sends those commands to the database.</span></span>  
  
 <span data-ttu-id="511e8-108">![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")</span><span class="sxs-lookup"><span data-stu-id="511e8-108">![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")</span></span>  
  
 <span data-ttu-id="511e8-109">下表概括了 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对象模型中最基本的元素及其与关系数据模型中的元素的关系：</span><span class="sxs-lookup"><span data-stu-id="511e8-109">The most fundamental elements in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model and their relationship to elements in the relational data model are summarized in the following table:</span></span>  
  
|<span data-ttu-id="511e8-110">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="511e8-110">LINQ to SQL Object Model</span></span>|<span data-ttu-id="511e8-111">关系数据模型</span><span class="sxs-lookup"><span data-stu-id="511e8-111">Relational Data Model</span></span>|  
|------------------------------|---------------------------|  
|<span data-ttu-id="511e8-112">实体类</span><span class="sxs-lookup"><span data-stu-id="511e8-112">Entity class</span></span>|<span data-ttu-id="511e8-113">表</span><span class="sxs-lookup"><span data-stu-id="511e8-113">Table</span></span>|  
|<span data-ttu-id="511e8-114">类成员</span><span class="sxs-lookup"><span data-stu-id="511e8-114">Class member</span></span>|<span data-ttu-id="511e8-115">列</span><span class="sxs-lookup"><span data-stu-id="511e8-115">Column</span></span>|  
|<span data-ttu-id="511e8-116">关联</span><span class="sxs-lookup"><span data-stu-id="511e8-116">Association</span></span>|<span data-ttu-id="511e8-117">外键关系</span><span class="sxs-lookup"><span data-stu-id="511e8-117">Foreign-key relationship</span></span>|  
|<span data-ttu-id="511e8-118">方法</span><span class="sxs-lookup"><span data-stu-id="511e8-118">Method</span></span>|<span data-ttu-id="511e8-119">存储过程或函数</span><span class="sxs-lookup"><span data-stu-id="511e8-119">Stored Procedure or Function</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="511e8-120">以下说明假定您已具备关系数据模型和规则方面的基础知识。</span><span class="sxs-lookup"><span data-stu-id="511e8-120">The following descriptions assume that you have a basic knowledge of the relational data model and rules.</span></span>  
  
## <a name="linq-to-sql-entity-classes-and-database-tables"></a><span data-ttu-id="511e8-121">LINQ to SQL 实体类与数据库表</span><span class="sxs-lookup"><span data-stu-id="511e8-121">LINQ to SQL Entity Classes and Database Tables</span></span>  
 <span data-ttu-id="511e8-122">在[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，由表示数据库表*实体类*。</span><span class="sxs-lookup"><span data-stu-id="511e8-122">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a database table is represented by an *entity class*.</span></span> <span data-ttu-id="511e8-123">实体类与你可能创建的任何其他类相似，只不过对实体类进行批注的方法是使用将该类与数据库表关联的特殊信息。</span><span class="sxs-lookup"><span data-stu-id="511e8-123">An entity class is like any other class you might create except that you annotate the class by using special information that associates the class with a database table.</span></span> <span data-ttu-id="511e8-124">您需通过向类声明中添加自定义属性 (<xref:System.Data.Linq.Mapping.TableAttribute>) 来进行这种批注，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="511e8-124">You make this annotation by adding a custom attribute (<xref:System.Data.Linq.Mapping.TableAttribute>) to your class declaration, as in the following example:</span></span>  
  
### <a name="example"></a><span data-ttu-id="511e8-125">示例</span><span class="sxs-lookup"><span data-stu-id="511e8-125">Example</span></span>  
 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 <span data-ttu-id="511e8-126">只有声明为表的类（即实体类）的实例才能保存到数据库中。</span><span class="sxs-lookup"><span data-stu-id="511e8-126">Only instances of classes declared as tables (that is, entity classes) can be saved to the database.</span></span>  
  
 <span data-ttu-id="511e8-127">有关详细信息，请参阅的表属性部分[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="511e8-127">For more information, see the Table Attribute section of [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
## <a name="linq-to-sql-class-members-and-database-columns"></a><span data-ttu-id="511e8-128">LINQ to SQL 类成员与数据库列</span><span class="sxs-lookup"><span data-stu-id="511e8-128">LINQ to SQL Class Members and Database Columns</span></span>  
 <span data-ttu-id="511e8-129">除了将类与表关联以外，您还需指定字段或属性来表示数据库列。</span><span class="sxs-lookup"><span data-stu-id="511e8-129">In addition to associating classes with tables, you designate fields or properties to represent database columns.</span></span> <span data-ttu-id="511e8-130">为此，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 定义了 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="511e8-130">For this purpose, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] defines the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute, as in the following example:</span></span>  
  
### <a name="example"></a><span data-ttu-id="511e8-131">示例</span><span class="sxs-lookup"><span data-stu-id="511e8-131">Example</span></span>  
 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 <span data-ttu-id="511e8-132">只有映射到列的字段和属性才能持久保存到数据库中，从数据库中也只能检索这样的字段和属性。</span><span class="sxs-lookup"><span data-stu-id="511e8-132">Only fields and properties mapped to columns are persisted to or retrieved from the database.</span></span> <span data-ttu-id="511e8-133">那些未声明为列的字段和属性被视为应用程序逻辑的瞬态部分。</span><span class="sxs-lookup"><span data-stu-id="511e8-133">Those not declared as columns are considered as transient parts of your application logic.</span></span>  
  
 <span data-ttu-id="511e8-134"><xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute) 具有各种属性 (Property)，您可以使用这些属性 (Property) 来自定义表示列的这些成员（例如，将某一成员指定为表示主键列）。</span><span class="sxs-lookup"><span data-stu-id="511e8-134">The <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute has a variety of properties that you can use to customize these members that represent columns (for example, designating a member as representing a primary key column).</span></span> <span data-ttu-id="511e8-135">有关详细信息，请参阅的列属性部分[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="511e8-135">For more information, see the Column Attribute section of [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
## <a name="linq-to-sql-associations-and-database-foreign-key-relationships"></a><span data-ttu-id="511e8-136">LINQ to SQL 关联与数据库外键关系</span><span class="sxs-lookup"><span data-stu-id="511e8-136">LINQ to SQL Associations and Database Foreign-key Relationships</span></span>  
 <span data-ttu-id="511e8-137">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，数据库关联（如外键到主键关系）是通过应用 <xref:System.Data.Linq.Mapping.AssociationAttribute> 属性表示的。</span><span class="sxs-lookup"><span data-stu-id="511e8-137">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you represent database associations (such as foreign-key to primary-key relationships) by applying the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span> <span data-ttu-id="511e8-138">在下面的代码段中，`Order` 类包含具有 `Customer` 属性 (Attribute) 的 <xref:System.Data.Linq.Mapping.AssociationAttribute> 属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="511e8-138">In the following segment of code, the `Order` class contains a `Customer` property that has an <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span> <span data-ttu-id="511e8-139">此属性 (Property) 及其属性 (Attribute) 为 `Order` 类提供了与 `Customer` 类的关系。</span><span class="sxs-lookup"><span data-stu-id="511e8-139">This property and its attribute provide the `Order` class with a relationship to the `Customer` class.</span></span>  
  
 <span data-ttu-id="511e8-140">下面的代码示例显示了 `Customer` 类中的 `Order` 属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="511e8-140">The following code example shows the `Customer` property from the `Order` class.</span></span>  
  
### <a name="example"></a><span data-ttu-id="511e8-141">示例</span><span class="sxs-lookup"><span data-stu-id="511e8-141">Example</span></span>  
 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 <span data-ttu-id="511e8-142">有关详细信息，请参阅的关联属性部分[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="511e8-142">For more information, see the Association Attribute section of [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
## <a name="linq-to-sql-methods-and-database-stored-procedures"></a><span data-ttu-id="511e8-143">LINQ to SQL 方法与数据库存储过程</span><span class="sxs-lookup"><span data-stu-id="511e8-143">LINQ to SQL Methods and Database Stored Procedures</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="511e8-144"> 支持存储过程和用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="511e8-144"> supports stored procedures and user-defined functions.</span></span> <span data-ttu-id="511e8-145">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，您应将数据库定义的这些抽象映射到客户端对象，以便您可以从客户端代码中以强类型化方式访问它们。</span><span class="sxs-lookup"><span data-stu-id="511e8-145">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you map these database-defined abstractions to client objects so that you can access them in a strongly typed manner from client code.</span></span> <span data-ttu-id="511e8-146">方法签名与数据库中定义的过程和函数的签名尽可能类似。</span><span class="sxs-lookup"><span data-stu-id="511e8-146">The method signatures resemble as closely as possible the signatures of the procedures and functions defined in the database.</span></span> <span data-ttu-id="511e8-147">您可以使用 IntelliSense 来查找这些方法。</span><span class="sxs-lookup"><span data-stu-id="511e8-147">You can use IntelliSense to discover these methods.</span></span>  
  
 <span data-ttu-id="511e8-148">通过调用映射的过程返回的结果集为强类型化的集合。</span><span class="sxs-lookup"><span data-stu-id="511e8-148">A result set that is returned by a call to a mapped procedure is a strongly typed collection.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="511e8-149"> 通过使用 <xref:System.Data.Linq.Mapping.FunctionAttribute> 和 <xref:System.Data.Linq.Mapping.ParameterAttribute> 属性将存储过程和函数映射到方法。</span><span class="sxs-lookup"><span data-stu-id="511e8-149"> maps stored procedures and functions to methods by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> and <xref:System.Data.Linq.Mapping.ParameterAttribute> attributes.</span></span> <span data-ttu-id="511e8-150">表示存储过程的方法与表示用户定义的函数的方法通过 <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A> 属性加以区分。</span><span class="sxs-lookup"><span data-stu-id="511e8-150">Methods representing stored procedures are distinguished from those representing user-defined functions by the <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A> property.</span></span> <span data-ttu-id="511e8-151">如果此属性设置为 `false`（默认值），则此方法表示存储过程。</span><span class="sxs-lookup"><span data-stu-id="511e8-151">If this property is set to `false` (the default), the method represents a stored procedure.</span></span> <span data-ttu-id="511e8-152">如果它设置为 `true`，则此方法表示数据库函数。</span><span class="sxs-lookup"><span data-stu-id="511e8-152">If it is set to `true`, the method represents a database function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="511e8-153">如果你使用的 Visual Studio，则可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]创建映射到存储的过程和用户定义函数的方法。</span><span class="sxs-lookup"><span data-stu-id="511e8-153">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create methods mapped to stored procedures and user-defined functions.</span></span>  
  
### <a name="example"></a><span data-ttu-id="511e8-154">示例</span><span class="sxs-lookup"><span data-stu-id="511e8-154">Example</span></span>  
 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 <span data-ttu-id="511e8-155">有关详细信息，请参阅函数特性、 存储过程属性和参数属性部分[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)和[存储过程](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="511e8-155">For more information, see the Function Attribute, Stored Procedure Attribute, and Parameter Attribute sections of [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) and [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="511e8-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="511e8-156">See Also</span></span>  
 [<span data-ttu-id="511e8-157">基于特性的映射</span><span class="sxs-lookup"><span data-stu-id="511e8-157">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="511e8-158">背景信息</span><span class="sxs-lookup"><span data-stu-id="511e8-158">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
