---
title: 常见问题
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 16c06ddade79c2b3a48401f5620431e46e18f5ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323239"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="f940b-102">常见问题</span><span class="sxs-lookup"><span data-stu-id="f940b-102">Frequently Asked Questions</span></span>
<span data-ttu-id="f940b-103">以下各节解答了您在实现 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 时可能遇到的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="f940b-103">The following sections answer some common issues that you might encounter when you implement [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="f940b-104">在解决其他问题[故障排除](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="f940b-104">Additional issues are addressed in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="cannot-connect"></a><span data-ttu-id="f940b-105">无法连接</span><span class="sxs-lookup"><span data-stu-id="f940b-105">Cannot Connect</span></span>  
 <span data-ttu-id="f940b-106">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-106">Q.</span></span> <span data-ttu-id="f940b-107">我无法连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="f940b-107">I cannot connect to my database.</span></span>  
  
 <span data-ttu-id="f940b-108">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-108">A.</span></span> <span data-ttu-id="f940b-109">请确保你的连接字符串正确，以及您的 SQL Server 实例正在运行。</span><span class="sxs-lookup"><span data-stu-id="f940b-109">Make sure your connection string is correct and that your SQL Server instance is running.</span></span> <span data-ttu-id="f940b-110">另请注意，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 要求启用命名管道协议。</span><span class="sxs-lookup"><span data-stu-id="f940b-110">Note also that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requires the Named Pipes protocol to be enabled.</span></span> <span data-ttu-id="f940b-111">有关详细信息，请参阅[通过演练学习](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)。</span><span class="sxs-lookup"><span data-stu-id="f940b-111">For more information, see [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
## <a name="changes-to-database-lost"></a><span data-ttu-id="f940b-112">对数据库的更改丢失</span><span class="sxs-lookup"><span data-stu-id="f940b-112">Changes to Database Lost</span></span>  
 <span data-ttu-id="f940b-113">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-113">Q.</span></span> <span data-ttu-id="f940b-114">我对数据库中的数据进行了更改，但是在重新运行应用程序时更改已丢失。</span><span class="sxs-lookup"><span data-stu-id="f940b-114">I made a change to data in the database, but when I reran my application, the change was no longer there.</span></span>  
  
 <span data-ttu-id="f940b-115">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-115">A.</span></span> <span data-ttu-id="f940b-116">请确保您调用了 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 来将结果保存到数据库。</span><span class="sxs-lookup"><span data-stu-id="f940b-116">Make sure that you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> to save results to the database.</span></span>  
  
## <a name="database-connection-open-how-long"></a><span data-ttu-id="f940b-117">数据库连接：打开多长时间？</span><span class="sxs-lookup"><span data-stu-id="f940b-117">Database Connection: Open How Long?</span></span>  
 <span data-ttu-id="f940b-118">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-118">Q.</span></span> <span data-ttu-id="f940b-119">我的数据库连接可以保持打开状态多长时间？</span><span class="sxs-lookup"><span data-stu-id="f940b-119">How long does my database connection remain open?</span></span>  
  
 <span data-ttu-id="f940b-120">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-120">A.</span></span> <span data-ttu-id="f940b-121">一个连接通常会一直保持打开状态，直至您使用完查询结果为止。</span><span class="sxs-lookup"><span data-stu-id="f940b-121">A connection typically remains open until you consume the query results.</span></span> <span data-ttu-id="f940b-122">如果您需要花时间处理所有结果并且愿意对结果进行缓存，请将 <xref:System.Linq.Enumerable.ToList%2A> 应用于查询。</span><span class="sxs-lookup"><span data-stu-id="f940b-122">If you expect to take time to process all the results and are not opposed to caching the results, apply <xref:System.Linq.Enumerable.ToList%2A> to the query.</span></span> <span data-ttu-id="f940b-123">在每个对象仅处理一次的常见方案中，流模型比 `DataReader` 和 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 都更为适合。</span><span class="sxs-lookup"><span data-stu-id="f940b-123">In common scenarios where each object is processed only one time, the streaming model is superior in both `DataReader` and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="f940b-124">连接使用的准确详细信息与以下内容有关：</span><span class="sxs-lookup"><span data-stu-id="f940b-124">The exact details of connection usage depend on the following:</span></span>  
  
-   <span data-ttu-id="f940b-125">使用连接对象构造 <xref:System.Data.Linq.DataContext> 时的连接状态。</span><span class="sxs-lookup"><span data-stu-id="f940b-125">Connection status if the <xref:System.Data.Linq.DataContext> is constructed with a connection object.</span></span>  
  
-   <span data-ttu-id="f940b-126">连接字符串设置（例如，启用多活动结果集 (MARS)）。</span><span class="sxs-lookup"><span data-stu-id="f940b-126">Connection string settings (for example, enabling Multiple Active Result Sets (MARS).</span></span> <span data-ttu-id="f940b-127">有关详细信息，请参阅[多个活动结果集 (MARS)](../../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)。</span><span class="sxs-lookup"><span data-stu-id="f940b-127">For more information, see [Multiple Active Result Sets (MARS)](../../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md).</span></span>  
  
## <a name="updating-without-querying"></a><span data-ttu-id="f940b-128">在不进行查询的情况下更新</span><span class="sxs-lookup"><span data-stu-id="f940b-128">Updating Without Querying</span></span>  
 <span data-ttu-id="f940b-129">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-129">Q.</span></span> <span data-ttu-id="f940b-130">是否可以在不先查询数据库的情况下更新表数据？</span><span class="sxs-lookup"><span data-stu-id="f940b-130">Can I update table data without first querying the database?</span></span>  
  
 <span data-ttu-id="f940b-131">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-131">A.</span></span> <span data-ttu-id="f940b-132">虽然 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 没有基于集的更新命令，但是可以使用以下方法之一进行更新而无需先进行查询：</span><span class="sxs-lookup"><span data-stu-id="f940b-132">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not have set-based update commands, you can use either of the following techniques to update without first querying:</span></span>  
  
-   <span data-ttu-id="f940b-133">使用 <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> 发送 SQL 代码。</span><span class="sxs-lookup"><span data-stu-id="f940b-133">Use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to send SQL code.</span></span>  
  
-   <span data-ttu-id="f940b-134">创建对象的新实例，并初始化所有影响更新的当前值（字段）。</span><span class="sxs-lookup"><span data-stu-id="f940b-134">Create a new instance of the object and initialize all the current values (fields) that affect the update.</span></span> <span data-ttu-id="f940b-135">然后使用 <xref:System.Data.Linq.DataContext> 将对象附加到 <xref:System.Data.Linq.Table%601.Attach%2A> 并修改您要更改的字段。</span><span class="sxs-lookup"><span data-stu-id="f940b-135">Then attach the object to the <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.Table%601.Attach%2A> and modify the field you want to change.</span></span>  
  
## <a name="unexpected-query-results"></a><span data-ttu-id="f940b-136">意外的查询结果</span><span class="sxs-lookup"><span data-stu-id="f940b-136">Unexpected Query Results</span></span>  
 <span data-ttu-id="f940b-137">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-137">Q.</span></span> <span data-ttu-id="f940b-138">我的查询返回了意外的结果。</span><span class="sxs-lookup"><span data-stu-id="f940b-138">My query is returning unexpected results.</span></span> <span data-ttu-id="f940b-139">如何检查所发生的情况？</span><span class="sxs-lookup"><span data-stu-id="f940b-139">How can I inspect what is occurring?</span></span>  
  
 <span data-ttu-id="f940b-140">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-140">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f940b-141">提供了几种工具用于检查其生成的 SQL 代码。</span><span class="sxs-lookup"><span data-stu-id="f940b-141">provides several tools for inspecting the SQL code it generates.</span></span> <span data-ttu-id="f940b-142">其中最重要的工具就是 <xref:System.Data.Linq.DataContext.Log%2A>。</span><span class="sxs-lookup"><span data-stu-id="f940b-142">One of the most important is <xref:System.Data.Linq.DataContext.Log%2A>.</span></span> <span data-ttu-id="f940b-143">有关详细信息，请参阅[调试支持](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)。</span><span class="sxs-lookup"><span data-stu-id="f940b-143">For more information, see [Debugging Support](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).</span></span>  
  
## <a name="unexpected-stored-procedure-results"></a><span data-ttu-id="f940b-144">意外的存储过程结果</span><span class="sxs-lookup"><span data-stu-id="f940b-144">Unexpected Stored Procedure Results</span></span>  
 <span data-ttu-id="f940b-145">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-145">Q.</span></span> <span data-ttu-id="f940b-146">我有一个存储过程，其返回值由 `MAX()` 进行计算。</span><span class="sxs-lookup"><span data-stu-id="f940b-146">I have a stored procedure whose return value is calculated by `MAX()`.</span></span> <span data-ttu-id="f940b-147">在将该存储过程拖动到 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]图面时，返回值不正确。</span><span class="sxs-lookup"><span data-stu-id="f940b-147">When I drag the stored procedure to the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] surface, the return value is not correct.</span></span>  
  
 <span data-ttu-id="f940b-148">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-148">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f940b-149">提供了两种方法来通过存储过程返回数据库生成的值：</span><span class="sxs-lookup"><span data-stu-id="f940b-149">provides two ways to return database-generated values by way of stored procedures:</span></span>  
  
-   <span data-ttu-id="f940b-150">通过命名输出结果。</span><span class="sxs-lookup"><span data-stu-id="f940b-150">By naming the output result.</span></span>  
  
-   <span data-ttu-id="f940b-151">通过显式指定输出参数。</span><span class="sxs-lookup"><span data-stu-id="f940b-151">By explicitly specifying an output parameter.</span></span>  
  
 <span data-ttu-id="f940b-152">下面是错误输出的示例。</span><span class="sxs-lookup"><span data-stu-id="f940b-152">The following is an example of incorrect output.</span></span> <span data-ttu-id="f940b-153">因为 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 无法映射结果，所以始终返回 0：</span><span class="sxs-lookup"><span data-stu-id="f940b-153">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot map the results, it always returns 0:</span></span>  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select max(i) from t where name like 'hello'`  
  
 `end`  
  
 <span data-ttu-id="f940b-154">下面是使用输出参数获得正确输出的示例：</span><span class="sxs-lookup"><span data-stu-id="f940b-154">The following is an example of correct output by using an output parameter:</span></span>  
  
 `create procedure proc2`  
  
 `@result int OUTPUT`  
  
 `as`  
  
 `select @result = MAX(i) from t where name like 'hello'`  
  
 `go`  
  
 <span data-ttu-id="f940b-155">下面是通过命名输出结果获得正确输出的示例：</span><span class="sxs-lookup"><span data-stu-id="f940b-155">The following is an example of correct output by naming the output result:</span></span>  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select nax(i) AS MaxResult from t where name like 'hello'`  
  
 `end`  
  
 <span data-ttu-id="f940b-156">有关详细信息，请参阅[自定义操作通过使用存储过程](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="f940b-156">For more information, see [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md).</span></span>  
  
## <a name="serialization-errors"></a><span data-ttu-id="f940b-157">序列化错误</span><span class="sxs-lookup"><span data-stu-id="f940b-157">Serialization Errors</span></span>  
 <span data-ttu-id="f940b-158">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-158">Q.</span></span> <span data-ttu-id="f940b-159">当我尝试进行序列化时，为什么会出现以下错误："...类型 'system.data.linq.changetracker + standardchangetracker' 未标记为可序列化。"</span><span class="sxs-lookup"><span data-stu-id="f940b-159">When I try to serialize, I get the following error: "Type 'System.Data.Linq.ChangeTracker+StandardChangeTracker' ... is not marked as serializable."</span></span>  
  
 <span data-ttu-id="f940b-160">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-160">A.</span></span> <span data-ttu-id="f940b-161">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中的代码生成支持 <xref:System.Runtime.Serialization.DataContractSerializer> 序列化，</span><span class="sxs-lookup"><span data-stu-id="f940b-161">Code generation in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports <xref:System.Runtime.Serialization.DataContractSerializer> serialization.</span></span> <span data-ttu-id="f940b-162">而不支持 <xref:System.Xml.Serialization.XmlSerializer> 或 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>。</span><span class="sxs-lookup"><span data-stu-id="f940b-162">It does not support <xref:System.Xml.Serialization.XmlSerializer> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="f940b-163">有关详细信息，请参阅[序列化](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)。</span><span class="sxs-lookup"><span data-stu-id="f940b-163">For more information, see [Serialization](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>  
  
## <a name="multiple-dbml-files"></a><span data-ttu-id="f940b-164">多个 DBML 文件</span><span class="sxs-lookup"><span data-stu-id="f940b-164">Multiple DBML Files</span></span>  
 <span data-ttu-id="f940b-165">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-165">Q.</span></span> <span data-ttu-id="f940b-166">如果我有多个 DBML 文件共享一些公用的表，我会收到一个编译器错误消息。</span><span class="sxs-lookup"><span data-stu-id="f940b-166">When I have multiple DBML files that share some tables in common, I get a compiler error.</span></span>  
  
 <span data-ttu-id="f940b-167">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-167">A.</span></span> <span data-ttu-id="f940b-168">设置**上下文 Namespace**并**实体 Namespace**中的属性[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]为每个 DBML 文件不同的值。</span><span class="sxs-lookup"><span data-stu-id="f940b-168">Set the **Context Namespace** and **Entity Namespace** properties from the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to a distinct value for each DBML file.</span></span> <span data-ttu-id="f940b-169">此方法可以避免名称/命名空间冲突。</span><span class="sxs-lookup"><span data-stu-id="f940b-169">This approach eliminates the name/namespace collision.</span></span>  
  
## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a><span data-ttu-id="f940b-170">避免在插入或更新时显式设置数据库生成的值</span><span class="sxs-lookup"><span data-stu-id="f940b-170">Avoiding Explicit Setting of Database-Generated Values on Insert or Update</span></span>  
 <span data-ttu-id="f940b-171">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-171">Q.</span></span> <span data-ttu-id="f940b-172">我的一个数据库表具有一个默认为 SQL `DateCreated` 的 `Getdate()` 列。</span><span class="sxs-lookup"><span data-stu-id="f940b-172">I have a database table with a `DateCreated` column that defaults to SQL `Getdate()`.</span></span> <span data-ttu-id="f940b-173">在我试图使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 插入新记录时，该值会设置为 `NULL`。</span><span class="sxs-lookup"><span data-stu-id="f940b-173">When I try to insert a new record by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the value gets set to `NULL`.</span></span> <span data-ttu-id="f940b-174">我希望其设置为数据库默认值。</span><span class="sxs-lookup"><span data-stu-id="f940b-174">I would expect it to be set to the database default.</span></span>  
  
 <span data-ttu-id="f940b-175">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-175">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f940b-176">会自动为标识（自动增加）和 rowguidcol（数据库生成的 GUID）以及时间戳列处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="f940b-176">handles this situation automatically for identity (auto-increment) and rowguidcol (database-generated GUID) and timestamp columns.</span></span> <span data-ttu-id="f940b-177">在其他情况下，您应手动设置<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> = `true`并<xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> = <xref:System.Data.Linq.Mapping.AutoSync.Always> / <xref:System.Data.Linq.Mapping.AutoSync.OnInsert> / <xref:System.Data.Linq.Mapping.AutoSync.OnUpdate>属性。</span><span class="sxs-lookup"><span data-stu-id="f940b-177">In other cases, you should manually set <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` and <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> properties.</span></span>  
  
## <a name="multiple-dataloadoptions"></a><span data-ttu-id="f940b-178">多个 DataLoadOptions</span><span class="sxs-lookup"><span data-stu-id="f940b-178">Multiple DataLoadOptions</span></span>  
 <span data-ttu-id="f940b-179">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-179">Q.</span></span> <span data-ttu-id="f940b-180">是否可以指定其他加载选项而不覆盖原先的选项？</span><span class="sxs-lookup"><span data-stu-id="f940b-180">Can I specify additional load options without overwriting the first?</span></span>  
  
 <span data-ttu-id="f940b-181">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-181">A.</span></span> <span data-ttu-id="f940b-182">可以。</span><span class="sxs-lookup"><span data-stu-id="f940b-182">Yes.</span></span> <span data-ttu-id="f940b-183">不会覆盖原先的选项，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="f940b-183">The first is not overwritten, as in the following example:</span></span>  
  
```vb  
Dim dlo As New DataLoadOptions()  
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)  
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)  
```  
  
```csharp  
DataLoadOptions dlo = new DataLoadOptions();  
dlo.LoadWith<Order>(o => o.Customer);  
dlo.LoadWith<Order>(o => o.OrderDetails);  
```  
  
## <a name="errors-using-sql-compact-35"></a><span data-ttu-id="f940b-184">使用 SQL Compact 3.5 时的错误</span><span class="sxs-lookup"><span data-stu-id="f940b-184">Errors Using SQL Compact 3.5</span></span>  
 <span data-ttu-id="f940b-185">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-185">Q.</span></span> <span data-ttu-id="f940b-186">在将表拖出 [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] 数据库时收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="f940b-186">I get an error when I drag tables out of a [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] database.</span></span>  
  
 <span data-ttu-id="f940b-187">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-187">A.</span></span> <span data-ttu-id="f940b-188">虽然 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 受 [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] 运行时支持，但它在[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]中不受支持。</span><span class="sxs-lookup"><span data-stu-id="f940b-188">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)], although the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime does.</span></span> <span data-ttu-id="f940b-189">在这种情况下，必须创建您自己的实体类并添加合适的属性。</span><span class="sxs-lookup"><span data-stu-id="f940b-189">In this situation, you must create your own entity classes and add the appropriate attributes.</span></span>  
  
## <a name="errors-in-inheritance-relationships"></a><span data-ttu-id="f940b-190">继承关系中的错误</span><span class="sxs-lookup"><span data-stu-id="f940b-190">Errors in Inheritance Relationships</span></span>  
 <span data-ttu-id="f940b-191">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-191">Q.</span></span> <span data-ttu-id="f940b-192">我使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]中的工具箱继承形状连接两个实体，但是收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="f940b-192">I used the toolbox inheritance shape in the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to connect two entities, but I get errors.</span></span>  
  
 <span data-ttu-id="f940b-193">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-193">A.</span></span> <span data-ttu-id="f940b-194">仅创建关系是不够的。</span><span class="sxs-lookup"><span data-stu-id="f940b-194">Creating the relationship is not enough.</span></span> <span data-ttu-id="f940b-195">还必须提供其他信息，例如鉴别器列、基类鉴别器值和派生类鉴别器值。</span><span class="sxs-lookup"><span data-stu-id="f940b-195">You must provide information such as the discriminator column, base class discriminator value, and derived class discriminator value.</span></span>  
  
## <a name="provider-model"></a><span data-ttu-id="f940b-196">提供程序模型</span><span class="sxs-lookup"><span data-stu-id="f940b-196">Provider Model</span></span>  
 <span data-ttu-id="f940b-197">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-197">Q.</span></span> <span data-ttu-id="f940b-198">是否有公共提供程序模型可用？</span><span class="sxs-lookup"><span data-stu-id="f940b-198">Is a public provider model available?</span></span>  
  
 <span data-ttu-id="f940b-199">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-199">A.</span></span> <span data-ttu-id="f940b-200">没有任何公共提供程序模型可用。</span><span class="sxs-lookup"><span data-stu-id="f940b-200">No public provider model is available.</span></span> <span data-ttu-id="f940b-201">在此期间，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]支持 SQL Server 和[!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)]仅。</span><span class="sxs-lookup"><span data-stu-id="f940b-201">At this time, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports SQL Server and [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] only.</span></span>  
  
## <a name="sql-injection-attacks"></a><span data-ttu-id="f940b-202">SQL 注入式攻击</span><span class="sxs-lookup"><span data-stu-id="f940b-202">SQL-Injection Attacks</span></span>  
 <span data-ttu-id="f940b-203">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-203">Q.</span></span> <span data-ttu-id="f940b-204">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 如何防范 SQL 注入式攻击？</span><span class="sxs-lookup"><span data-stu-id="f940b-204">How is [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] protected from SQL-injection attacks?</span></span>  
  
 <span data-ttu-id="f940b-205">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-205">A.</span></span> <span data-ttu-id="f940b-206">对于通过串联用户输入而组成的传统 SQL 查询，SQL 注入已成为重大风险。</span><span class="sxs-lookup"><span data-stu-id="f940b-206">SQL injection has been a significant risk for traditional SQL queries formed by concatenating user input.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f940b-207">通过在查询中使用 <xref:System.Data.SqlClient.SqlParameter> 来避免这种注入。</span><span class="sxs-lookup"><span data-stu-id="f940b-207">avoids such injection by using <xref:System.Data.SqlClient.SqlParameter> in queries.</span></span> <span data-ttu-id="f940b-208">用户输入会转换为参数值。</span><span class="sxs-lookup"><span data-stu-id="f940b-208">User input is turned into parameter values.</span></span> <span data-ttu-id="f940b-209">此方法可防止通过客户输入使用恶意命令。</span><span class="sxs-lookup"><span data-stu-id="f940b-209">This approach prevents malicious commands from being used from customer input.</span></span>  
  
## <a name="changing-read-only-flag-in-dbml-files"></a><span data-ttu-id="f940b-210">更改 DBML 文件中的只读标志</span><span class="sxs-lookup"><span data-stu-id="f940b-210">Changing Read-only Flag in DBML Files</span></span>  
 <span data-ttu-id="f940b-211">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-211">Q.</span></span> <span data-ttu-id="f940b-212">如何在从 DBML 文件创建对象模型时消除某些属性中的设置器？</span><span class="sxs-lookup"><span data-stu-id="f940b-212">How do I eliminate setters from some properties when I create an object model from a DBML file?</span></span>  
  
 <span data-ttu-id="f940b-213">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-213">A.</span></span> <span data-ttu-id="f940b-214">对于此高级方案，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f940b-214">Take the following steps for this advanced scenario:</span></span>  
  
1. <span data-ttu-id="f940b-215">在 .dbml 文件中，通过将 <xref:System.Data.Linq.ITable.IsReadOnly%2A> 标志更改为 `True` 来修改属性。</span><span class="sxs-lookup"><span data-stu-id="f940b-215">In the .dbml file, modify the property by changing the <xref:System.Data.Linq.ITable.IsReadOnly%2A> flag to `True`.</span></span>  
  
2. <span data-ttu-id="f940b-216">添加一个分部类。</span><span class="sxs-lookup"><span data-stu-id="f940b-216">Add a partial class.</span></span> <span data-ttu-id="f940b-217">为只读成员创建一个带参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="f940b-217">Create a constructor with parameters for the read-only members.</span></span>  
  
3. <span data-ttu-id="f940b-218">检查默认的 <xref:System.Data.Linq.Mapping.UpdateCheck> 值 (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) 以确定该值对于您的应用程序是否正确。</span><span class="sxs-lookup"><span data-stu-id="f940b-218">Review the default <xref:System.Data.Linq.Mapping.UpdateCheck> value (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) to determine whether that is the correct value for your application.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="f940b-219">如果使用的[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]在 Visual Studio 中，可能会覆盖所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f940b-219">If you are using the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] in Visual Studio, your changes might be overwritten.</span></span>  
  
## <a name="aptca"></a><span data-ttu-id="f940b-220">APTCA</span><span class="sxs-lookup"><span data-stu-id="f940b-220">APTCA</span></span>  
 <span data-ttu-id="f940b-221">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-221">Q.</span></span> <span data-ttu-id="f940b-222">System.Data.Linq 是否标记为供部分受信任的代码使用？</span><span class="sxs-lookup"><span data-stu-id="f940b-222">Is System.Data.Linq marked for use by partially trusted code?</span></span>  
  
 <span data-ttu-id="f940b-223">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-223">A.</span></span> <span data-ttu-id="f940b-224">是，System.Data.Linq.dll 程序集属于那些使用 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 属性标记的 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 程序集。</span><span class="sxs-lookup"><span data-stu-id="f940b-224">Yes, the System.Data.Linq.dll assembly is among those [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="f940b-225">如果没有此标记，则 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 中的程序集将仅供完全受信任的代码使用。</span><span class="sxs-lookup"><span data-stu-id="f940b-225">Without this marking, assemblies in the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] are intended for use only by fully trusted code.</span></span>  
  
 <span data-ttu-id="f940b-226">中的主要方案[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，允许部分受信任调用方是能够[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]程序集访问从 Web 应用程序，其中*信任*配置为 Medium。</span><span class="sxs-lookup"><span data-stu-id="f940b-226">The principal scenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] for allowing partially trusted callers is to enable the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly to be accessed from Web applications, where the *trust* configuration is Medium.</span></span>  
  
## <a name="mapping-data-from-multiple-tables"></a><span data-ttu-id="f940b-227">映射来自多个表的数据</span><span class="sxs-lookup"><span data-stu-id="f940b-227">Mapping Data from Multiple Tables</span></span>  
 <span data-ttu-id="f940b-228">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-228">Q.</span></span> <span data-ttu-id="f940b-229">我的实体中的数据来自多个表。</span><span class="sxs-lookup"><span data-stu-id="f940b-229">The data in my entity comes from multiple tables.</span></span> <span data-ttu-id="f940b-230">如果映射这些数据？</span><span class="sxs-lookup"><span data-stu-id="f940b-230">How do I map it?</span></span>  
  
 <span data-ttu-id="f940b-231">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-231">A.</span></span> <span data-ttu-id="f940b-232">您可以在数据库中创建一个视图并将实体映射到该视图。</span><span class="sxs-lookup"><span data-stu-id="f940b-232">You can create a view in a database and map the entity to the view.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f940b-233">会为视图生成 SQL，与它为表生成 SQL 相同。</span><span class="sxs-lookup"><span data-stu-id="f940b-233">generates the same SQL for views as it does for tables.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f940b-234">这种情况下的视图用法有一些限制。</span><span class="sxs-lookup"><span data-stu-id="f940b-234">The use of views in this scenario has limitations.</span></span> <span data-ttu-id="f940b-235">当基础视图支持在 <xref:System.Data.Linq.Table%601> 上执行的操作时，此方法最为安全。</span><span class="sxs-lookup"><span data-stu-id="f940b-235">This approach works most safely when the operations performed on <xref:System.Data.Linq.Table%601> are supported by the underlying view.</span></span> <span data-ttu-id="f940b-236">只有您知道要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f940b-236">Only you know which operations are intended.</span></span> <span data-ttu-id="f940b-237">例如，大多数应用程序是只读的并且还有相当多执行`Create` / `Update` / `Delete`操作只能通过使用存储过程，针对视图。</span><span class="sxs-lookup"><span data-stu-id="f940b-237">For example, most applications are read-only, and another sizeable number perform `Create`/`Update`/`Delete` operations only by using stored procedures against views.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="f940b-238">连接池</span><span class="sxs-lookup"><span data-stu-id="f940b-238">Connection Pooling</span></span>  
 <span data-ttu-id="f940b-239">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-239">Q.</span></span> <span data-ttu-id="f940b-240">是否具有对 <xref:System.Data.Linq.DataContext> 池有所帮助的构造？</span><span class="sxs-lookup"><span data-stu-id="f940b-240">Is there a construct that can help with <xref:System.Data.Linq.DataContext> pooling?</span></span>  
  
 <span data-ttu-id="f940b-241">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-241">A.</span></span> <span data-ttu-id="f940b-242">请不要试图重用 <xref:System.Data.Linq.DataContext> 的实例。</span><span class="sxs-lookup"><span data-stu-id="f940b-242">Do not try to reuse instances of <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="f940b-243">每个 <xref:System.Data.Linq.DataContext> 都会保持对应一个特定编辑/查询会话的状态（包括标识缓存）。</span><span class="sxs-lookup"><span data-stu-id="f940b-243">Each <xref:System.Data.Linq.DataContext> maintains state (including an identity cache) for one particular edit/query session.</span></span> <span data-ttu-id="f940b-244">若要获取基于数据库当前状态的新实例，请使用新的 <xref:System.Data.Linq.DataContext>。</span><span class="sxs-lookup"><span data-stu-id="f940b-244">To obtain new instances based on the current state of the database, use a new <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="f940b-245">仍然可以使用基础 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 连接池。</span><span class="sxs-lookup"><span data-stu-id="f940b-245">You can still use underlying [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] connection pooling.</span></span> <span data-ttu-id="f940b-246">有关详细信息，请参阅 [SQL Server 连接池 (ADO.NET)](../../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)。</span><span class="sxs-lookup"><span data-stu-id="f940b-246">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
## <a name="second-datacontext-is-not-updated"></a><span data-ttu-id="f940b-247">第二个 DataContext 未更新</span><span class="sxs-lookup"><span data-stu-id="f940b-247">Second DataContext Is Not Updated</span></span>  
 <span data-ttu-id="f940b-248">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-248">Q.</span></span> <span data-ttu-id="f940b-249">我使用 <xref:System.Data.Linq.DataContext> 的一个实例存储数据库中的值。</span><span class="sxs-lookup"><span data-stu-id="f940b-249">I used one instance of <xref:System.Data.Linq.DataContext> to store values in the database.</span></span> <span data-ttu-id="f940b-250">但是，相同数据库上的另一个 <xref:System.Data.Linq.DataContext> 未反映更新的值。</span><span class="sxs-lookup"><span data-stu-id="f940b-250">However, a second <xref:System.Data.Linq.DataContext> on the same database does not reflect the updated values.</span></span> <span data-ttu-id="f940b-251">第二个 <xref:System.Data.Linq.DataContext> 实例似乎返回缓存的值。</span><span class="sxs-lookup"><span data-stu-id="f940b-251">The second <xref:System.Data.Linq.DataContext> instance seems to return cached values.</span></span>  
  
 <span data-ttu-id="f940b-252">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-252">A.</span></span> <span data-ttu-id="f940b-253">此行为是有意安排的。</span><span class="sxs-lookup"><span data-stu-id="f940b-253">This behavior is by design.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f940b-254">会继续返回您在第一个实例中看到的相同实例/值。</span><span class="sxs-lookup"><span data-stu-id="f940b-254">continues to return the same instances/values that you saw in the first instance.</span></span> <span data-ttu-id="f940b-255">在进行更新时使用开放式并发。</span><span class="sxs-lookup"><span data-stu-id="f940b-255">When you make updates, you use optimistic concurrency.</span></span> <span data-ttu-id="f940b-256">原始数据用于检查当前数据库状态，以确定该数据实际上仍未更改。</span><span class="sxs-lookup"><span data-stu-id="f940b-256">The original data is used to check against the current database state to assert that it is in fact still unchanged.</span></span> <span data-ttu-id="f940b-257">如果该数据已更改，则会发生冲突，您的应用程序必须解决该冲突。</span><span class="sxs-lookup"><span data-stu-id="f940b-257">If it has changed, a conflict occurs and your application must resolve it.</span></span> <span data-ttu-id="f940b-258">您的应用程序可以选择将原始状态重置为当前数据库状态并尝试再次更新。</span><span class="sxs-lookup"><span data-stu-id="f940b-258">One option of your application is to reset the original state to the current database state and to try the update again.</span></span> <span data-ttu-id="f940b-259">有关详细信息，请参阅[如何：管理更改冲突](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)。</span><span class="sxs-lookup"><span data-stu-id="f940b-259">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
 <span data-ttu-id="f940b-260">您也可以将 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> 设置为 false，这样可以关闭缓存和更改跟踪。</span><span class="sxs-lookup"><span data-stu-id="f940b-260">You can also set <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to false, which turns off caching and change tracking.</span></span> <span data-ttu-id="f940b-261">然后便可以在每次查询时检索最新值。</span><span class="sxs-lookup"><span data-stu-id="f940b-261">You can then retrieve the latest values every time that you query.</span></span>  
  
## <a name="cannot-call-submitchanges-in-read-only-mode"></a><span data-ttu-id="f940b-262">无法在只读模式下调用 SubmitChanges</span><span class="sxs-lookup"><span data-stu-id="f940b-262">Cannot Call SubmitChanges in Read-only Mode</span></span>  
 <span data-ttu-id="f940b-263">问：</span><span class="sxs-lookup"><span data-stu-id="f940b-263">Q.</span></span> <span data-ttu-id="f940b-264">当我试图在只读模式下调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="f940b-264">When I try to call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in read-only mode, I get an error.</span></span>  
  
 <span data-ttu-id="f940b-265">答：</span><span class="sxs-lookup"><span data-stu-id="f940b-265">A.</span></span> <span data-ttu-id="f940b-266">只读模式关闭了上下文跟踪更改的功能。</span><span class="sxs-lookup"><span data-stu-id="f940b-266">Read-only mode turns off the ability of the context to track changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f940b-267">请参阅</span><span class="sxs-lookup"><span data-stu-id="f940b-267">See also</span></span>

- [<span data-ttu-id="f940b-268">引用</span><span class="sxs-lookup"><span data-stu-id="f940b-268">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="f940b-269">疑难解答</span><span class="sxs-lookup"><span data-stu-id="f940b-269">Troubleshooting</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)
- [<span data-ttu-id="f940b-270">LINQ to SQL 中的安全性</span><span class="sxs-lookup"><span data-stu-id="f940b-270">Security in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)
