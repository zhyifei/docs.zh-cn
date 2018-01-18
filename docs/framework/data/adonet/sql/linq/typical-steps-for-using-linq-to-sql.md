---
title: "使用 LINQ to SQL 的典型步骤"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3aedef610d8ad3f743b346a46059b15d917cf7ca
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="typical-steps-for-using-linq-to-sql"></a><span data-ttu-id="a7d60-102">使用 LINQ to SQL 的典型步骤</span><span class="sxs-lookup"><span data-stu-id="a7d60-102">Typical Steps for Using LINQ to SQL</span></span>
<span data-ttu-id="a7d60-103">若要实现 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序，请按照本主题后面部分说明的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a7d60-103">To implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application, you follow the steps described later in this topic.</span></span> <span data-ttu-id="a7d60-104">请注意，很多步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="a7d60-104">Note that many steps are optional.</span></span> <span data-ttu-id="a7d60-105">您可以以对象模型的默认状态使用它，这种可能性很高。</span><span class="sxs-lookup"><span data-stu-id="a7d60-105">It is very possible that you can use your object model in its default state.</span></span>  
  
 <span data-ttu-id="a7d60-106">为了很快入手，请使用 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 来创建对象模型并开始编写查询代码。</span><span class="sxs-lookup"><span data-stu-id="a7d60-106">For a really fast start, use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model and start coding your queries.</span></span>  
  
## <a name="creating-the-object-model"></a><span data-ttu-id="a7d60-107">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="a7d60-107">Creating the Object Model</span></span>  
 <span data-ttu-id="a7d60-108">第一步是用现有关系数据库的元数据创建对象模型。</span><span class="sxs-lookup"><span data-stu-id="a7d60-108">The first step is to create an object model from the metadata of an existing relational database.</span></span> <span data-ttu-id="a7d60-109">对象模型按照开发人员所用的编程语言来表示数据库。</span><span class="sxs-lookup"><span data-stu-id="a7d60-109">The object model represents the database according to the programming language of the developer.</span></span> <span data-ttu-id="a7d60-110">有关详细信息，请参阅[LINQ to SQL 对象模型](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-110">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
### <a name="1-select-a-tool-to-create-the-model"></a><span data-ttu-id="a7d60-111">1.选择用于创建模型的工具。</span><span class="sxs-lookup"><span data-stu-id="a7d60-111">1. Select a tool to create the model.</span></span>  
 <span data-ttu-id="a7d60-112">有三种工具可用于创建模型。</span><span class="sxs-lookup"><span data-stu-id="a7d60-112">Three tools are available for creating the model.</span></span>  
  
-   <span data-ttu-id="a7d60-113">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7d60-113">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]</span></span>  
  
     <span data-ttu-id="a7d60-114">此设计器提供了用于从现有数据库创建对象模型的丰富用户界面。</span><span class="sxs-lookup"><span data-stu-id="a7d60-114">This designer provides a rich user interface for creating an object model from an existing database.</span></span> <span data-ttu-id="a7d60-115">此工具是 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] IDE 的一部分，最适合小型或中型数据库。</span><span class="sxs-lookup"><span data-stu-id="a7d60-115">This tool is part of the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] IDE, and is best suited to small or medium databases.</span></span>  
  
-   <span data-ttu-id="a7d60-116">SQLMetal 代码生成工具</span><span class="sxs-lookup"><span data-stu-id="a7d60-116">The SQLMetal code-generation tool</span></span>  
  
     <span data-ttu-id="a7d60-117">此命令行实用工具提供了与 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]略微不同的一组选项。</span><span class="sxs-lookup"><span data-stu-id="a7d60-117">This command-line utility provides a slightly different set of options from the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].</span></span> <span data-ttu-id="a7d60-118">最好使用此工具对大型数据库进行建模。</span><span class="sxs-lookup"><span data-stu-id="a7d60-118">Modeling large databases is best done by using this tool.</span></span> <span data-ttu-id="a7d60-119">有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-119">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
-   <span data-ttu-id="a7d60-120">代码编辑器</span><span class="sxs-lookup"><span data-stu-id="a7d60-120">A code editor</span></span>  
  
     <span data-ttu-id="a7d60-121">您可以通过使用 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]代码编辑器或其他编辑器编写自己的代码。</span><span class="sxs-lookup"><span data-stu-id="a7d60-121">You can write your own code by using either the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] code editor or another editor.</span></span> <span data-ttu-id="a7d60-122">我们建议，在您具有现有数据库且可以使用 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]或 SQLMetal 工具时不要使用这种方法，因为这种方法容易出错。</span><span class="sxs-lookup"><span data-stu-id="a7d60-122">We do not recommend this approach, which can be prone to errors, when you have an existing database and can use either the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] or the SQLMetal tool.</span></span> <span data-ttu-id="a7d60-123">但是，代码编辑器在改进或修改你已通过使用其他工具生成的代码方面非常有用。</span><span class="sxs-lookup"><span data-stu-id="a7d60-123">However, the code editor can be valuable for refining or modifying code you have already generated by using other tools.</span></span> <span data-ttu-id="a7d60-124">有关详细信息，请参阅[如何： 使用代码编辑器自定义实体类](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-124">For more information, see [How to: Customize Entity Classes by Using the Code Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md).</span></span>  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a><span data-ttu-id="a7d60-125">2.选择您要生成的代码类型。</span><span class="sxs-lookup"><span data-stu-id="a7d60-125">2. Select the kind of code you want to generate.</span></span>  
  
-   <span data-ttu-id="a7d60-126">用于基于属性的映射的 C# 或 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 源代码文件。</span><span class="sxs-lookup"><span data-stu-id="a7d60-126">A C# or [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] source code file for attribute-based mapping.</span></span>  
  
     <span data-ttu-id="a7d60-127">然后将此代码文件加入您的 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 项目中。</span><span class="sxs-lookup"><span data-stu-id="a7d60-127">You then include this code file in your [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] project.</span></span> <span data-ttu-id="a7d60-128">有关详细信息，请参阅[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-128">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
-   <span data-ttu-id="a7d60-129">用于外部映射的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="a7d60-129">An XML file for external mapping.</span></span>  
  
     <span data-ttu-id="a7d60-130">通过使用此方法，你可以将映射元数据放在应用程序代码外部。</span><span class="sxs-lookup"><span data-stu-id="a7d60-130">By using this approach, you can keep the mapping metadata out of your application code.</span></span> <span data-ttu-id="a7d60-131">有关详细信息，请参阅[外部映射](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-131">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7d60-132">[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]不支持生成外部映射文件。</span><span class="sxs-lookup"><span data-stu-id="a7d60-132">The [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] does not support the generation of external mapping files.</span></span> <span data-ttu-id="a7d60-133">您必须使用 SQLMetal 工具来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="a7d60-133">You must use the SQLMetal tool to implement this feature.</span></span>  
  
-   <span data-ttu-id="a7d60-134">DBML 文件，您可以在生成最终代码文件之前修改此文件。</span><span class="sxs-lookup"><span data-stu-id="a7d60-134">A DBML file, which you can modify before generating a final code file.</span></span>  
  
     <span data-ttu-id="a7d60-135">这是一项高级功能。</span><span class="sxs-lookup"><span data-stu-id="a7d60-135">This is an advanced feature.</span></span>  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a><span data-ttu-id="a7d60-136">3.改进代码文件以反映您的应用程序的需要。</span><span class="sxs-lookup"><span data-stu-id="a7d60-136">3. Refine the code file to reflect the needs of your application.</span></span>  
 <span data-ttu-id="a7d60-137">为此，您可以使用 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]或代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="a7d60-137">For this purpose, you can use either the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] or the code editor.</span></span>  
  
## <a name="using-the-object-model"></a><span data-ttu-id="a7d60-138">使用对象模型</span><span class="sxs-lookup"><span data-stu-id="a7d60-138">Using the Object Model</span></span>  
 <span data-ttu-id="a7d60-139">下图显示了在两层方案中开发人员与数据之间的关系。</span><span class="sxs-lookup"><span data-stu-id="a7d60-139">The following illustration shows the relationship between the developer and the data in a two-tier scenario.</span></span> <span data-ttu-id="a7d60-140">有关其他方案，请参阅[N 层和远程应用程序而 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-140">For other scenarios, see [N-Tier and Remote Applications with LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="a7d60-141">![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")</span><span class="sxs-lookup"><span data-stu-id="a7d60-141">![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")</span></span>  
  
 <span data-ttu-id="a7d60-142">既然您已经有了对象模型，您就可以在该模型中描述信息请求和操作数据。</span><span class="sxs-lookup"><span data-stu-id="a7d60-142">Now that you have the object model, you describe information requests and manipulate data within that model.</span></span> <span data-ttu-id="a7d60-143">您应从对象模型中的对象和属性的角度来考虑，而不是从数据库的行和列的角度来考虑。</span><span class="sxs-lookup"><span data-stu-id="a7d60-143">You think in terms of the objects and properties in your object model and not in terms of the rows and columns of the database.</span></span> <span data-ttu-id="a7d60-144">您不是直接对数据库进行操作。</span><span class="sxs-lookup"><span data-stu-id="a7d60-144">You do not deal directly with the database.</span></span>  
  
 <span data-ttu-id="a7d60-145">当您指示 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 执行您已描述的查询或对您已操作的数据调用 `SubmitChanges()` 时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会用数据库的语言与数据库通信。</span><span class="sxs-lookup"><span data-stu-id="a7d60-145">When you instruct [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to either execute a query that you have described or call `SubmitChanges()` on data that you have manipulated, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] communicates with the database in the language of the database.</span></span>  
  
 <span data-ttu-id="a7d60-146">以下内容代表使用您已创建的对象模型的典型步骤。</span><span class="sxs-lookup"><span data-stu-id="a7d60-146">The following represents typical steps for using the object model that you have created.</span></span>  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a><span data-ttu-id="a7d60-147">1.创建查询以从数据库中检索信息。</span><span class="sxs-lookup"><span data-stu-id="a7d60-147">1. Create queries to retrieve information from the database.</span></span>  
 <span data-ttu-id="a7d60-148">有关详细信息，请参阅[查询概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)和[查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-148">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md) and [Query Examples](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md).</span></span>  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a><span data-ttu-id="a7d60-149">2.重写 Insert、Update 和 Delete 的默认行为。</span><span class="sxs-lookup"><span data-stu-id="a7d60-149">2. Override default behaviors for Insert, Update, and Delete.</span></span>  
 <span data-ttu-id="a7d60-150">这一步是可选的。</span><span class="sxs-lookup"><span data-stu-id="a7d60-150">This step is optional.</span></span> <span data-ttu-id="a7d60-151">有关详细信息，请参阅[自定义插入、 更新和删除操作](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-151">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a><span data-ttu-id="a7d60-152">3.设置适当的选项以检测和报告并发冲突。</span><span class="sxs-lookup"><span data-stu-id="a7d60-152">3. Set appropriate options to detect and report concurrency conflicts.</span></span>  
 <span data-ttu-id="a7d60-153">您可以保留模型用于处理并发冲突的默认值，也可以根据您的需要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="a7d60-153">You can leave your model with its default values for handling concurrency conflicts, or you can change it to suit your purposes.</span></span> <span data-ttu-id="a7d60-154">有关详细信息，请参阅[如何： 指定该成员进行测试并发冲突](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)和[如何： 指定当并发异常引发](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-154">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) and [How to: Specify When Concurrency Exceptions are Thrown](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).</span></span>  
  
### <a name="4-establish-an-inheritance-hierarchy"></a><span data-ttu-id="a7d60-155">4.建立继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="a7d60-155">4. Establish an inheritance hierarchy.</span></span>  
 <span data-ttu-id="a7d60-156">这一步是可选的。</span><span class="sxs-lookup"><span data-stu-id="a7d60-156">This step is optional.</span></span> <span data-ttu-id="a7d60-157">有关详细信息，请参阅[继承支持](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-157">For more information, see [Inheritance Support](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).</span></span>  
  
### <a name="5-provide-an-appropriate-user-interface"></a><span data-ttu-id="a7d60-158">5.提供合适的用户界面。</span><span class="sxs-lookup"><span data-stu-id="a7d60-158">5. Provide an appropriate user interface.</span></span>  
 <span data-ttu-id="a7d60-159">这一步是可选的，取决于您的应用程序的使用方式。</span><span class="sxs-lookup"><span data-stu-id="a7d60-159">This step is optional, and depends on how your application will be used.</span></span>  
  
### <a name="6-debug-and-test-your-application"></a><span data-ttu-id="a7d60-160">6.调试并测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7d60-160">6. Debug and test your application.</span></span>  
 <span data-ttu-id="a7d60-161">有关详细信息，请参阅[调试支持](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a7d60-161">For more information, see [Debugging Support](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d60-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7d60-162">See Also</span></span>  
 [<span data-ttu-id="a7d60-163">入门</span><span class="sxs-lookup"><span data-stu-id="a7d60-163">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 [<span data-ttu-id="a7d60-164">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="a7d60-164">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="a7d60-165">存储过程</span><span class="sxs-lookup"><span data-stu-id="a7d60-165">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
