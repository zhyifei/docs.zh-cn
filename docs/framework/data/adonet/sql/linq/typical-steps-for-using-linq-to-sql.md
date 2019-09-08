---
title: 使用 LINQ to SQL 的典型步骤
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: c7964c821a838e027302cddce704d86cc6a34f66
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792342"
---
# <a name="typical-steps-for-using-linq-to-sql"></a><span data-ttu-id="d66d5-102">使用 LINQ to SQL 的典型步骤</span><span class="sxs-lookup"><span data-stu-id="d66d5-102">Typical Steps for Using LINQ to SQL</span></span>
<span data-ttu-id="d66d5-103">若要实现 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序，请按照本主题后面部分说明的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="d66d5-103">To implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application, you follow the steps described later in this topic.</span></span> <span data-ttu-id="d66d5-104">请注意，很多步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="d66d5-104">Note that many steps are optional.</span></span> <span data-ttu-id="d66d5-105">您可以以对象模型的默认状态使用它，这种可能性很高。</span><span class="sxs-lookup"><span data-stu-id="d66d5-105">It is very possible that you can use your object model in its default state.</span></span>  
  
 <span data-ttu-id="d66d5-106">为实现非常快速的入门，请使用对象关系设计器来创建对象模型并开始编写查询代码。</span><span class="sxs-lookup"><span data-stu-id="d66d5-106">For a really fast start, use the Object Relational Designer to create your object model and start coding your queries.</span></span>  
  
## <a name="creating-the-object-model"></a><span data-ttu-id="d66d5-107">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="d66d5-107">Creating the Object Model</span></span>  
 <span data-ttu-id="d66d5-108">第一步是用现有关系数据库的元数据创建对象模型。</span><span class="sxs-lookup"><span data-stu-id="d66d5-108">The first step is to create an object model from the metadata of an existing relational database.</span></span> <span data-ttu-id="d66d5-109">对象模型按照开发人员所用的编程语言来表示数据库。</span><span class="sxs-lookup"><span data-stu-id="d66d5-109">The object model represents the database according to the programming language of the developer.</span></span> <span data-ttu-id="d66d5-110">有关详细信息，请参阅[LINQ to SQL 对象模型](the-linq-to-sql-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-110">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
### <a name="1-select-a-tool-to-create-the-model"></a><span data-ttu-id="d66d5-111">1.选择用于创建模型的工具。</span><span class="sxs-lookup"><span data-stu-id="d66d5-111">1. Select a tool to create the model.</span></span>  
 <span data-ttu-id="d66d5-112">有三种工具可用于创建模型。</span><span class="sxs-lookup"><span data-stu-id="d66d5-112">Three tools are available for creating the model.</span></span>  
  
- <span data-ttu-id="d66d5-113">对象关系设计器</span><span class="sxs-lookup"><span data-stu-id="d66d5-113">The Object Relational Designer</span></span>  
  
     <span data-ttu-id="d66d5-114">此设计器提供了用于从现有数据库创建对象模型的丰富用户界面。</span><span class="sxs-lookup"><span data-stu-id="d66d5-114">This designer provides a rich user interface for creating an object model from an existing database.</span></span> <span data-ttu-id="d66d5-115">此工具是 Visual Studio IDE 的一部分，最适合小型或中型数据库。</span><span class="sxs-lookup"><span data-stu-id="d66d5-115">This tool is part of the Visual Studio IDE, and is best suited to small or medium databases.</span></span>  
  
- <span data-ttu-id="d66d5-116">SQLMetal 代码生成工具</span><span class="sxs-lookup"><span data-stu-id="d66d5-116">The SQLMetal code-generation tool</span></span>  
  
     <span data-ttu-id="d66d5-117">此命令行实用工具提供一组与 O/R 设计器稍有不同的选项。</span><span class="sxs-lookup"><span data-stu-id="d66d5-117">This command-line utility provides a slightly different set of options from the O/R Designer.</span></span> <span data-ttu-id="d66d5-118">最好使用此工具对大型数据库进行建模。</span><span class="sxs-lookup"><span data-stu-id="d66d5-118">Modeling large databases is best done by using this tool.</span></span> <span data-ttu-id="d66d5-119">有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../tools/sqlmetal-exe-code-generation-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-119">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
- <span data-ttu-id="d66d5-120">代码编辑器</span><span class="sxs-lookup"><span data-stu-id="d66d5-120">A code editor</span></span>  
  
     <span data-ttu-id="d66d5-121">您可以使用 Visual Studio 代码编辑器或其他编辑器编写自己的代码。</span><span class="sxs-lookup"><span data-stu-id="d66d5-121">You can write your own code by using either the Visual Studio code editor or another editor.</span></span> <span data-ttu-id="d66d5-122">如果你有现有数据库并可以使用 O/R 设计器或 SQLMetal 工具，我们不建议使用这种方法，这种方法很容易出错。</span><span class="sxs-lookup"><span data-stu-id="d66d5-122">We do not recommend this approach, which can be prone to errors, when you have an existing database and can use either the O/R Designer or the SQLMetal tool.</span></span> <span data-ttu-id="d66d5-123">但是，代码编辑器在改进或修改你已通过使用其他工具生成的代码方面非常有用。</span><span class="sxs-lookup"><span data-stu-id="d66d5-123">However, the code editor can be valuable for refining or modifying code you have already generated by using other tools.</span></span> <span data-ttu-id="d66d5-124">有关详细信息，请参阅[如何：使用代码编辑器](how-to-customize-entity-classes-by-using-the-code-editor.md)自定义实体类。</span><span class="sxs-lookup"><span data-stu-id="d66d5-124">For more information, see [How to: Customize Entity Classes by Using the Code Editor](how-to-customize-entity-classes-by-using-the-code-editor.md).</span></span>  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a><span data-ttu-id="d66d5-125">2.选择你要生成的代码类型。</span><span class="sxs-lookup"><span data-stu-id="d66d5-125">2. Select the kind of code you want to generate.</span></span>  
  
- <span data-ttu-id="d66d5-126">C#或 Visual Basic 的源代码文件，用于基于属性的映射。</span><span class="sxs-lookup"><span data-stu-id="d66d5-126">A C# or Visual Basic source code file for attribute-based mapping.</span></span>  
  
     <span data-ttu-id="d66d5-127">然后将此代码文件包含在 Visual Studio 项目中。</span><span class="sxs-lookup"><span data-stu-id="d66d5-127">You then include this code file in your Visual Studio project.</span></span> <span data-ttu-id="d66d5-128">有关详细信息，请参阅[基于属性的映射](attribute-based-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-128">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="d66d5-129">用于外部映射的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d66d5-129">An XML file for external mapping.</span></span>  
  
     <span data-ttu-id="d66d5-130">通过使用此方法，你可以将映射元数据放在应用程序代码外部。</span><span class="sxs-lookup"><span data-stu-id="d66d5-130">By using this approach, you can keep the mapping metadata out of your application code.</span></span> <span data-ttu-id="d66d5-131">有关详细信息，请参阅[外部映射](external-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-131">For more information, see [External Mapping](external-mapping.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d66d5-132">O/R 设计器不支持生成外部映射文件。</span><span class="sxs-lookup"><span data-stu-id="d66d5-132">The O/R Designer does not support the generation of external mapping files.</span></span> <span data-ttu-id="d66d5-133">您必须使用 SQLMetal 工具来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="d66d5-133">You must use the SQLMetal tool to implement this feature.</span></span>  
  
- <span data-ttu-id="d66d5-134">DBML 文件，你可以在生成最终代码文件之前修改此文件。</span><span class="sxs-lookup"><span data-stu-id="d66d5-134">A DBML file, which you can modify before generating a final code file.</span></span>  
  
     <span data-ttu-id="d66d5-135">这是一项高级功能。</span><span class="sxs-lookup"><span data-stu-id="d66d5-135">This is an advanced feature.</span></span>  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a><span data-ttu-id="d66d5-136">3.改进代码文件以反映你的应用程序的需要。</span><span class="sxs-lookup"><span data-stu-id="d66d5-136">3. Refine the code file to reflect the needs of your application.</span></span>  
 <span data-ttu-id="d66d5-137">为此，可以使用 O/R 设计器或代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="d66d5-137">For this purpose, you can use either the O/R Designer or the code editor.</span></span>  
  
## <a name="using-the-object-model"></a><span data-ttu-id="d66d5-138">使用对象模型</span><span class="sxs-lookup"><span data-stu-id="d66d5-138">Using the Object Model</span></span>  
 <span data-ttu-id="d66d5-139">下图显示了在两层方案中开发人员与数据之间的关系。</span><span class="sxs-lookup"><span data-stu-id="d66d5-139">The following illustration shows the relationship between the developer and the data in a two-tier scenario.</span></span> <span data-ttu-id="d66d5-140">对于其他方案，请参阅[具有 LINQ to SQL 的 N 层和远程应用程序](n-tier-and-remote-applications-with-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-140">For other scenarios, see [N-Tier and Remote Applications with LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).</span></span>  
  
 ![显示 Linq 对象模型的屏幕截图。](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 <span data-ttu-id="d66d5-142">既然您已经有了对象模型，您就可以在该模型中描述信息请求和操作数据。</span><span class="sxs-lookup"><span data-stu-id="d66d5-142">Now that you have the object model, you describe information requests and manipulate data within that model.</span></span> <span data-ttu-id="d66d5-143">您应从对象模型中的对象和属性的角度来考虑，而不是从数据库的行和列的角度来考虑。</span><span class="sxs-lookup"><span data-stu-id="d66d5-143">You think in terms of the objects and properties in your object model and not in terms of the rows and columns of the database.</span></span> <span data-ttu-id="d66d5-144">您不是直接对数据库进行操作。</span><span class="sxs-lookup"><span data-stu-id="d66d5-144">You do not deal directly with the database.</span></span>  
  
 <span data-ttu-id="d66d5-145">当您指示 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 执行您已描述的查询或对您已操作的数据调用 `SubmitChanges()` 时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会用数据库的语言与数据库通信。</span><span class="sxs-lookup"><span data-stu-id="d66d5-145">When you instruct [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to either execute a query that you have described or call `SubmitChanges()` on data that you have manipulated, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] communicates with the database in the language of the database.</span></span>  
  
 <span data-ttu-id="d66d5-146">以下内容代表使用您已创建的对象模型的典型步骤。</span><span class="sxs-lookup"><span data-stu-id="d66d5-146">The following represents typical steps for using the object model that you have created.</span></span>  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a><span data-ttu-id="d66d5-147">1.创建查询以从数据库中检索信息。</span><span class="sxs-lookup"><span data-stu-id="d66d5-147">1. Create queries to retrieve information from the database.</span></span>  
 <span data-ttu-id="d66d5-148">有关详细信息，请参阅[查询概念](query-concepts.md)和[查询示例](query-examples.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-148">For more information, see [Query Concepts](query-concepts.md) and [Query Examples](query-examples.md).</span></span>  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a><span data-ttu-id="d66d5-149">2.重写 Insert、Update 和 Delete 的默认行为。</span><span class="sxs-lookup"><span data-stu-id="d66d5-149">2. Override default behaviors for Insert, Update, and Delete.</span></span>  
 <span data-ttu-id="d66d5-150">这一步是可选的。</span><span class="sxs-lookup"><span data-stu-id="d66d5-150">This step is optional.</span></span> <span data-ttu-id="d66d5-151">有关详细信息，请参阅[自定义插入、更新和删除操作](customizing-insert-update-and-delete-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-151">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a><span data-ttu-id="d66d5-152">3.设置适当的选项以检测和报告并发冲突。</span><span class="sxs-lookup"><span data-stu-id="d66d5-152">3. Set appropriate options to detect and report concurrency conflicts.</span></span>  
 <span data-ttu-id="d66d5-153">您可以保留模型用于处理并发冲突的默认值，也可以根据您的需要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="d66d5-153">You can leave your model with its default values for handling concurrency conflicts, or you can change it to suit your purposes.</span></span> <span data-ttu-id="d66d5-154">有关详细信息，请参阅[如何：指定针对并发冲突](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)对哪些成员进行测试，以及[如何执行以下操作：指定何时引发](how-to-specify-when-concurrency-exceptions-are-thrown.md)并发异常。</span><span class="sxs-lookup"><span data-stu-id="d66d5-154">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) and [How to: Specify When Concurrency Exceptions are Thrown](how-to-specify-when-concurrency-exceptions-are-thrown.md).</span></span>  
  
### <a name="4-establish-an-inheritance-hierarchy"></a><span data-ttu-id="d66d5-155">4.建立继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="d66d5-155">4. Establish an inheritance hierarchy.</span></span>  
 <span data-ttu-id="d66d5-156">这一步是可选的。</span><span class="sxs-lookup"><span data-stu-id="d66d5-156">This step is optional.</span></span> <span data-ttu-id="d66d5-157">有关详细信息，请参阅[继承支持](inheritance-support.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-157">For more information, see [Inheritance Support](inheritance-support.md).</span></span>  
  
### <a name="5-provide-an-appropriate-user-interface"></a><span data-ttu-id="d66d5-158">5.提供合适的用户界面。</span><span class="sxs-lookup"><span data-stu-id="d66d5-158">5. Provide an appropriate user interface.</span></span>  
 <span data-ttu-id="d66d5-159">这一步是可选的，取决于您的应用程序的使用方式。</span><span class="sxs-lookup"><span data-stu-id="d66d5-159">This step is optional, and depends on how your application will be used.</span></span>  
  
### <a name="6-debug-and-test-your-application"></a><span data-ttu-id="d66d5-160">6.调试并测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="d66d5-160">6. Debug and test your application.</span></span>  
 <span data-ttu-id="d66d5-161">有关详细信息，请参阅[调试支持](debugging-support.md)。</span><span class="sxs-lookup"><span data-stu-id="d66d5-161">For more information, see [Debugging Support](debugging-support.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d66d5-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="d66d5-162">See also</span></span>

- [<span data-ttu-id="d66d5-163">入门</span><span class="sxs-lookup"><span data-stu-id="d66d5-163">Getting Started</span></span>](getting-started.md)
- [<span data-ttu-id="d66d5-164">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="d66d5-164">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="d66d5-165">存储过程</span><span class="sxs-lookup"><span data-stu-id="d66d5-165">Stored Procedures</span></span>](stored-procedures.md)
