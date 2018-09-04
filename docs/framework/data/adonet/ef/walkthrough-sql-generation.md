---
title: 演练：SQL 生成
ms.date: 03/30/2017
ms.assetid: 16c38aaa-9927-4f3c-ab0f-81636cce57a3
ms.openlocfilehash: 5551eb4088e7529c61d5c517fed6877c23ae12f2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510495"
---
# <a name="walkthrough-sql-generation"></a><span data-ttu-id="a6522-102">演练：SQL 生成</span><span class="sxs-lookup"><span data-stu-id="a6522-102">Walkthrough: SQL Generation</span></span>
<span data-ttu-id="a6522-103">本主题说明了如何中进行 SQL 生成[示例提供程序](https://go.microsoft.com/fwlink/?LinkId=180616)。</span><span class="sxs-lookup"><span data-stu-id="a6522-103">This topic illustrates how SQL generation occurs in the [Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616).</span></span> <span data-ttu-id="a6522-104">下面的 Entity SQL 查询使用随示例提供程序提供的模型：</span><span class="sxs-lookup"><span data-stu-id="a6522-104">The following Entity SQL query uses the model that is included with the sample provider:</span></span>  
  
```  
SELECT  j1.ProductId, j1.ProductName, j1.CategoryName, j2.ShipCountry, j2.ProductId  
FROM (  SELECT P.ProductName, P.ProductId, P.Category.CategoryName  
        FROM NorthwindEntities.Products AS P) as j1  
INNER JOIN (SELECT OD.ProductId, OD.Order.ShipCountry as ShipCountry  
            FROM NorthwindEntities.OrderDetails AS OD) as j2  
            ON j1.ProductId == j2.ProductId   
```  
  
 <span data-ttu-id="a6522-105">此查询生成以下传递给提供程序的输出命令目录树：</span><span class="sxs-lookup"><span data-stu-id="a6522-105">The query produces the following output command tree that is passed to the provider:</span></span>  
  
```  
DbQueryCommandTree  
|_Parameters  
|_Query : Collection{Record['C1'=Edm.Int32, 'ProductID'=Edm.Int32, 'ProductName'=Edm.String, 'CategoryName'=Edm.String, 'ShipCountry'=Edm.String, 'ProductID1'=Edm.Int32]}  
  |_Project  
    |_Input : 'Join4'  
    | |_InnerJoin  
    |   |_Left : 'Join1'  
    |   | |_LeftOuterJoin  
    |   |   |_Left : 'Extent1'  
    |   |   | |_Scan : dbo.Products  
    |   |   |_Right : 'Extent2'  
    |   |   | |_Scan : dbo.Categories  
    |   |   |_JoinCondition  
    |   |     |_  
    |   |       |_Var(Extent1).CategoryID  
    |   |       |_=  
    |   |       |_Var(Extent2).CategoryID  
    |   |_Right : 'Join3'  
    |   | |_LeftOuterJoin  
    |   |   |_Left : 'Extent3'  
    |   |   | |_Scan : dbo.OrderDetails  
    |   |   |_Right : 'Join2'  
    |   |   | |_LeftOuterJoin  
    |   |   |   |_Left : 'Extent4'  
    |   |   |   | |_Scan : dbo.Orders  
    |   |   |   |_Right : 'Extent5'  
    |   |   |   | |_Scan : dbo.InternationalOrders  
    |   |   |   |_JoinCondition  
    |   |   |     |_  
    |   |   |       |_Var(Extent4).OrderID  
    |   |   |       |_=  
    |   |   |       |_Var(Extent5).OrderID  
    |   |   |_JoinCondition  
    |   |     |_  
    |   |       |_Var(Extent3).OrderID  
    |   |       |_=  
    |   |       |_Var(Join2).Extent4.OrderID  
    |   |_JoinCondition  
    |     |_  
    |       |_Var(Join1).Extent1.ProductID  
    |       |_=  
    |       |_Var(Join3).Extent3.ProductID  
    |_Projection  
      |_NewInstance : Record['C1'=Edm.Int32, 'ProductID'=Edm.Int32, 'ProductName'=Edm.String, 'CategoryName'=Edm.String, 'ShipCountry'=Edm.String, 'ProductID1'=Edm.Int32]  
        |_Column : 'C1'  
        | |_1  
        |_Column : 'ProductID'  
        | |_Var(Join4).Join1.Extent1.ProductID  
        |_Column : 'ProductName'  
        | |_Var(Join4).Join1.Extent1.ProductName  
        |_Column : 'CategoryName'  
        | |_Var(Join4).Join1.Extent2.CategoryName  
        |_Column : 'ShipCountry'  
        | |_Var(Join4).Join3.Join2.Extent4.ShipCountry  
        |_Column : 'ProductID1'  
          |_Var(Join4).Join3.Extent3.ProductID  
```  
  
 <span data-ttu-id="a6522-106">本主题描述如何将此输出命令目录树转换成下列 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="a6522-106">This topic describes how to translate this output command tree into the following SQL statements.</span></span>  
  
```  
SELECT   
1 AS [C1],   
[Extent1].[ProductID] AS [ProductID],   
[Extent1].[ProductName] AS [ProductName],   
[Extent2].[CategoryName] AS [CategoryName],   
[Join3].[ShipCountry] AS [ShipCountry],   
[Join3].[ProductID] AS [ProductID1]  
FROM   [dbo].[Products] AS [Extent1]  
LEFT OUTER JOIN [dbo].[Categories] AS [Extent2] ON [Extent1].[CategoryID] = [Extent2].[CategoryID]  
INNER JOIN    
(SELECT [Extent3].[OrderID] AS [OrderID1], [Extent3].[ProductID] AS [ProductID], [Extent3].[UnitPrice] AS [UnitPrice], [Extent3].[Quantity] AS [Quantity], [Extent3].[Discount] AS [Discount], [Join2].[OrderID2], [Join2].[CustomerID], [Join2].[EmployeeID], [Join2].[OrderDate], [Join2].[RequiredDate], [Join2].[ShippedDate], [Join2].[Freight], [Join2].[ShipName], [Join2].[ShipAddress], [Join2].[ShipCity], [Join2].[ShipRegion], [Join2].[ShipPostalCode], [Join2].[ShipCountry], [Join2].[OrderID3], [Join2].[CustomsDescription], [Join2].[ExciseTax]  
FROM  [dbo].[OrderDetails] AS [Extent3]  
LEFT OUTER JOIN    
      (SELECT [Extent4].[OrderID] AS [OrderID2], [Extent4].[CustomerID] AS [CustomerID], [Extent4].[EmployeeID] AS [EmployeeID], [Extent4].[OrderDate] AS [OrderDate], [Extent4].[RequiredDate] AS [RequiredDate], [Extent4].[ShippedDate] AS [ShippedDate], [Extent4].[Freight] AS [Freight], [Extent4].[ShipName] AS [ShipName], [Extent4].[ShipAddress] AS [ShipAddress], [Extent4].[ShipCity] AS [ShipCity], [Extent4].[ShipRegion] AS [ShipRegion], [Extent4].[ShipPostalCode] AS [ShipPostalCode], [Extent4].[ShipCountry] AS [ShipCountry], [Extent5].[OrderID] AS [OrderID3], [Extent5].[CustomsDescription] AS [CustomsDescription], [Extent5].[ExciseTax] AS [ExciseTax]  
FROM  [dbo].[Orders] AS [Extent4]  
LEFT OUTER JOIN [dbo].[InternationalOrders] AS [Extent5] ON [Extent4].[OrderID] = [Extent5].[OrderID]   
      ) AS [Join2] ON [Extent3].[OrderID] = [Join2].[OrderID2]   
   ) AS [Join3] ON [Extent1].[ProductID] = [Join3].[ProductID]  
```  
  
## <a name="first-phase-of-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="a6522-107">SQL 生成的第一阶段：访问表达式树</span><span class="sxs-lookup"><span data-stu-id="a6522-107">First Phase of SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="a6522-108">下图说明访问者的初始空状态。</span><span class="sxs-lookup"><span data-stu-id="a6522-108">The following figure illustrates the initial empty state of the visitor.</span></span>  <span data-ttu-id="a6522-109">本主题只演示与演练说明相关的属性。</span><span class="sxs-lookup"><span data-stu-id="a6522-109">Throughout this topic, only the properties relevant to the walkthrough explanation are shown.</span></span>  
  
 <span data-ttu-id="a6522-110">![Diagram](../../../../../docs/framework/data/adonet/ef/media/430180f5-4fb9-4bc3-8589-d566512d9703.gif "430180f5-4fb9-4bc3-8589-d566512d9703")</span><span class="sxs-lookup"><span data-stu-id="a6522-110">![Diagram](../../../../../docs/framework/data/adonet/ef/media/430180f5-4fb9-4bc3-8589-d566512d9703.gif "430180f5-4fb9-4bc3-8589-d566512d9703")</span></span>  
  
 <span data-ttu-id="a6522-111">访问 Project 节点时，将通过其输入 (Join4) 调用 VisitInputExpression，这将触发通过 VisitJoinExpression 方法访问 Join4。</span><span class="sxs-lookup"><span data-stu-id="a6522-111">When the Project  node is visited, VisitInputExpression is called over its input (Join4), which triggers the visit of Join4 by the method VisitJoinExpression.</span></span> <span data-ttu-id="a6522-112">由于这是最顶端联接，因此 IsParentAJoin 返回 false，在 SELECT 语句堆栈上创建并推送新的 SqlSelectStatement(SelectStatement0)。</span><span class="sxs-lookup"><span data-stu-id="a6522-112">Because this is a topmost join, IsParentAJoin returns false and a new SqlSelectStatement (SelectStatement0) is created and pushed on the SELECT statement stack.</span></span> <span data-ttu-id="a6522-113">此外，在符号表中输入一个新范围 (scope0)。</span><span class="sxs-lookup"><span data-stu-id="a6522-113">Also, a new scope (scope0) is entered in the symbol table.</span></span> <span data-ttu-id="a6522-114">在访问该联接的第一个（左侧）输入之前，将在 IsParentAJoin 堆栈上推送“true”。</span><span class="sxs-lookup"><span data-stu-id="a6522-114">Before the first (left) input of the join is visited, 'true' is pushed on the IsParentAJoin stack.</span></span> <span data-ttu-id="a6522-115">下图中显示了刚好在访问作为 Join4 的左输入的 Join1 之前的那一刻访问者的状态。</span><span class="sxs-lookup"><span data-stu-id="a6522-115">Right before Join1, which is the left input of Join4, is visited, the state of the visitor is as shown in the next figure.</span></span>  
  
 <span data-ttu-id="a6522-116">![Diagram](../../../../../docs/framework/data/adonet/ef/media/406d4f5f-6166-44ea-8e74-c5001d5d5d79.gif "406d4f5f-6166-44ea-8e74-c5001d5d5d79")</span><span class="sxs-lookup"><span data-stu-id="a6522-116">![Diagram](../../../../../docs/framework/data/adonet/ef/media/406d4f5f-6166-44ea-8e74-c5001d5d5d79.gif "406d4f5f-6166-44ea-8e74-c5001d5d5d79")</span></span>  
  
 <span data-ttu-id="a6522-117">通过 Join4 调用联接访问方法时，IsParentAJoin 为 true，因此它重用当前的选择语句 SelectStatement0。</span><span class="sxs-lookup"><span data-stu-id="a6522-117">When the join visit method is invoked over Join4, IsParentAJoin is true, thus it reuses the current select statement SelectStatement0.</span></span> <span data-ttu-id="a6522-118">输入一个新范围 (scope1)。</span><span class="sxs-lookup"><span data-stu-id="a6522-118">A new scope is entered (scope1).</span></span> <span data-ttu-id="a6522-119">在访问该联接的左侧子级 Extent1 之前，将在 IsParentAJoin 堆栈上推送另一个“true”。</span><span class="sxs-lookup"><span data-stu-id="a6522-119">Before visiting its left child, Extent1, another true is pushed on the IsParentAJoin stack.</span></span>  
  
 <span data-ttu-id="a6522-120">访问 Extent1 时，由于 IsParentAJoin 返回 true，因此它返回包含“[dbo].[Products]”的 SqlBuilder。</span><span class="sxs-lookup"><span data-stu-id="a6522-120">When Extent1 is visited, because IsParentAJoin returns true, it returns a SqlBuilder containing "[dbo].[Products]".</span></span> <span data-ttu-id="a6522-121">控制权将返回给访问 Join4 的方法。</span><span class="sxs-lookup"><span data-stu-id="a6522-121">The control returns to the method visiting Join4.</span></span> <span data-ttu-id="a6522-122">从 IsParentAJoin 中弹出一项，并调用 ProcessJoinInputResult，这会将访问 Extent1 的结果追加到 SelectStatement0 的 From 子句。</span><span class="sxs-lookup"><span data-stu-id="a6522-122">An entry is popped from IsParentAJoin, and ProcessJoinInputResult is called, which appends the result of visiting Extent1 to the From clause of SelectStatement0.</span></span> <span data-ttu-id="a6522-123">将创建输入绑定名称“Extent1”的新的 From 符号 symbol_Extent1 并将其添加到 SelectStatement0 的 FromExtents，另外还将“As”和 symbol_Extent1 追加到 From 子句中。</span><span class="sxs-lookup"><span data-stu-id="a6522-123">A new from symbol, symbol_Extent1, for the input binding name "Extent1" is created, added to the FromExtents of SelectStatement0, and also "As" and  symbol_Extent1 are appended to the from clause.</span></span> <span data-ttu-id="a6522-124">向 AllExtentNames 中添加一个对应于“Extent1”的新项，其值为 0。</span><span class="sxs-lookup"><span data-stu-id="a6522-124">A new entry is added to AllExtentNames for "Extent1" with the value of 0.</span></span> <span data-ttu-id="a6522-125">将一个新项添加到符号表的当前范围中，以便将“Extent1”与其符号 symbol_Extent1 相关联。</span><span class="sxs-lookup"><span data-stu-id="a6522-125">A new entry is added to the current scope in the symbol table to associate "Extent1" with its symbol symbol_Extent1.</span></span> <span data-ttu-id="a6522-126">此外，将 Symbol_Extent1 添加到 SqlSelectStatement 的 AllJoinExtents。</span><span class="sxs-lookup"><span data-stu-id="a6522-126">Symbol_Extent1 is also added to the AllJoinExtents of the SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="a6522-127">在访问 Join1 的右侧输入之前，将“LEFT OUTER JOIN”添加到 SelectStatement0 的 From 子句。</span><span class="sxs-lookup"><span data-stu-id="a6522-127">Before the right input of Join1 is visited, "LEFT OUTER JOIN" is added to the From clause of SelectStatement0.</span></span> <span data-ttu-id="a6522-128">由于右侧输入是一个 Scan 表达式，因此再一次将 true 推送到 IsParentAJoin 堆栈。</span><span class="sxs-lookup"><span data-stu-id="a6522-128">Because the right input is a Scan expression, true is again pushed to the IsParentAJoin stack.</span></span> <span data-ttu-id="a6522-129">下图显示了在访问右侧输入之前的状态。</span><span class="sxs-lookup"><span data-stu-id="a6522-129">The state before visiting the right input as shown in the next figure.</span></span>  
  
 <span data-ttu-id="a6522-130">![Diagram](../../../../../docs/framework/data/adonet/ef/media/ca62c31b-7ff6-4836-b209-e16166304fdc.gif "ca62c31b-7ff6-4836-b209-e16166304fdc")</span><span class="sxs-lookup"><span data-stu-id="a6522-130">![Diagram](../../../../../docs/framework/data/adonet/ef/media/ca62c31b-7ff6-4836-b209-e16166304fdc.gif "ca62c31b-7ff6-4836-b209-e16166304fdc")</span></span>  
  
 <span data-ttu-id="a6522-131">按照处理左侧输入的相同方式处理右侧输入。</span><span class="sxs-lookup"><span data-stu-id="a6522-131">The right input is processed in the same way as the left input.</span></span> <span data-ttu-id="a6522-132">下图显示了访问右侧输入之后的状态。</span><span class="sxs-lookup"><span data-stu-id="a6522-132">The state after visiting the right input is shown in the next figure.</span></span>  
  
 <span data-ttu-id="a6522-133">![Diagram](../../../../../docs/framework/data/adonet/ef/media/cd2afa99-7256-4c63-aaa9-c2d13f18a3d8.gif "cd2afa99-7256-4c63-aaa9-c2d13f18a3d8")</span><span class="sxs-lookup"><span data-stu-id="a6522-133">![Diagram](../../../../../docs/framework/data/adonet/ef/media/cd2afa99-7256-4c63-aaa9-c2d13f18a3d8.gif "cd2afa99-7256-4c63-aaa9-c2d13f18a3d8")</span></span>  
  
 <span data-ttu-id="a6522-134">在 IsParentAJoin 堆栈上推送下一个“false”，并处理联接条件 Var(Extent1).CategoryID == Var(Extent2).CategoryID。</span><span class="sxs-lookup"><span data-stu-id="a6522-134">Next "false" is pushed on the IsParentAJoin stack and the join condition Var(Extent1).CategoryID == Var(Extent2).CategoryID is processed.</span></span> <span data-ttu-id="a6522-135">在符号表中进行查找之后，Var(Extenent1) 解析为 <symbol_Extent1>。</span><span class="sxs-lookup"><span data-stu-id="a6522-135">Var(Extenent1) is resolved to <symbol_Extent1> after a look up in the symbol table.</span></span> <span data-ttu-id="a6522-136">由于该实例解析为一个简单符号，Var(Extent1) 进行处理后。类别 Id、 与 SqlBuilder \<symbol1 >。"返回"类别 id。</span><span class="sxs-lookup"><span data-stu-id="a6522-136">Because the instance is resolved to a simple Symbol, as a result of processing Var(Extent1).CategoryID, a SqlBuilder with \<symbol1>."CategoryID" is returned.</span></span> <span data-ttu-id="a6522-137">比较的另一侧也采用类似方式处理，将访问联接条件的结果追加到 SelectStatement1 的 FROM 子句，并从 IsParentAJoin 堆栈中弹出“false”值。</span><span class="sxs-lookup"><span data-stu-id="a6522-137">Similarly the other side of the comparison is processed, and the result of visiting the join condition is appended to the FROM clause of SelectStatement1 and the value "false" is popped from the IsParentAJoin stack.</span></span>  
  
 <span data-ttu-id="a6522-138">就这样完成了对 Join1 的全部处理，并从符号表中弹出一个范围。</span><span class="sxs-lookup"><span data-stu-id="a6522-138">With this, Join1 has completely been processed, and a scope is popped from the symbol table.</span></span>  
  
 <span data-ttu-id="a6522-139">控制权将返回给正在处理的 Join4，即 Join1 的父级。</span><span class="sxs-lookup"><span data-stu-id="a6522-139">Control returns to processing Join4, the parent of Join1.</span></span> <span data-ttu-id="a6522-140">由于子级重用了 Select 语句，因此 Join1 范围由单个联接符号 <joinSymbol_Join1> 替代。</span><span class="sxs-lookup"><span data-stu-id="a6522-140">Because the child reused the Select statement, the Join1 extents are replaced with a single Join symbol <joinSymbol_Join1>.</span></span> <span data-ttu-id="a6522-141">此外，将一个新项添加到符号表中，以便将 Join1 与 <joinSymbol_Join1> 相关联。</span><span class="sxs-lookup"><span data-stu-id="a6522-141">Also a new entry is added to the symbol table to associate Join1 with <joinSymbol_Join1>.</span></span>  
  
 <span data-ttu-id="a6522-142">下一个要处理的节点是 Join3，即 Join4 的第二个子级。</span><span class="sxs-lookup"><span data-stu-id="a6522-142">The next node to be processed is Join3, the second child of Join4.</span></span> <span data-ttu-id="a6522-143">由于 Join3 是右侧子级，因此将“false”推送到 IsParentAJoin 堆栈。</span><span class="sxs-lookup"><span data-stu-id="a6522-143">As it is a right child, "false" is pushed to the IsParentAJoin stack.</span></span> <span data-ttu-id="a6522-144">下图中说明了访问者此时的状态。</span><span class="sxs-lookup"><span data-stu-id="a6522-144">The state of the visitor at this point is illustrated in the next figure.</span></span>  
  
 <span data-ttu-id="a6522-145">![Diagram](../../../../../docs/framework/data/adonet/ef/media/1ec61ed3-fcdd-4649-9089-24385be7e423.gif "1ec61ed3-fcdd-4649-9089-24385be7e423")</span><span class="sxs-lookup"><span data-stu-id="a6522-145">![Diagram](../../../../../docs/framework/data/adonet/ef/media/1ec61ed3-fcdd-4649-9089-24385be7e423.gif "1ec61ed3-fcdd-4649-9089-24385be7e423")</span></span>  
  
 <span data-ttu-id="a6522-146">对于 Join3，IsParentAJoin 返回 false，并需要启动一个新的 SqlSelectStatement (SelectStatement1)，将其推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="a6522-146">For Join3, IsParentAJoin returns false and needs to start a new SqlSelectStatement (SelectStatement1) and push it on the stack.</span></span> <span data-ttu-id="a6522-147">按照处理前面的联接的方式继续处理，将一个新范围推送到堆栈上，并处理子级。</span><span class="sxs-lookup"><span data-stu-id="a6522-147">Processing continues as it did with the previous the previous joins, a new scope is pushed on the stack and the children are processed.</span></span> <span data-ttu-id="a6522-148">左侧子级是一个 Extent (Extent3)，右侧子级是一个还需要启动新的 SqlSelectStatement (SelectStatement2) 的联接 (Join2)。</span><span class="sxs-lookup"><span data-stu-id="a6522-148">The left child is an Extent (Extent3) and the right child is a join (Join2) which also needs to start a new SqlSelectStatement: SelectStatement2.</span></span> <span data-ttu-id="a6522-149">Join2 上的子级也是 Extent，并聚合成 SelectStatement2。</span><span class="sxs-lookup"><span data-stu-id="a6522-149">The children on Join2 are Extents as well and are aggregated into SelectStatement2.</span></span>  
  
 <span data-ttu-id="a6522-150">下图显示了刚好在访问 Join2 之后但在完成其后续处理 (ProcessJoinInputResult) 之前的那一刻访问者的状态：</span><span class="sxs-lookup"><span data-stu-id="a6522-150">The state of the visitor right after Join2 is visited, but before its post-processing (ProcessJoinInputResult) is done is shown in the next figure:</span></span>  
  
 <span data-ttu-id="a6522-151">![关系图](../../../../../docs/framework/data/adonet/ef/media/7510346f-8b09-4c99-b411-40af239c3c4d.gif "7510346f-8b09-4c99-b411-40af239c3c4d")</span><span class="sxs-lookup"><span data-stu-id="a6522-151">![Diagram](../../../../../docs/framework/data/adonet/ef/media/7510346f-8b09-4c99-b411-40af239c3c4d.gif "7510346f-8b09-4c99-b411-40af239c3c4d")</span></span>  
  
 <span data-ttu-id="a6522-152">在上图中，SelectStatement2 显示为可自由浮动，原因是它已从堆栈中弹出，但尚未由父级进行后续处理。</span><span class="sxs-lookup"><span data-stu-id="a6522-152">In the previous figure, SelectStatement2 is shown as free floating because it was popped out of the stack, but not yet post processed by the parent.</span></span> <span data-ttu-id="a6522-153">需要将它添加到父级的 FROM 部分，但它没有 SELECT 子句，并不是完整的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="a6522-153">It needs to be added to the FROM part of the parent, but it is not a complete SQL statement without a SELECT clause.</span></span> <span data-ttu-id="a6522-154">因此，此时将由 AddDefaultColumns 方法将默认列（由 SelectStatement2 输入生成的所有列）添加到选择列表中。</span><span class="sxs-lookup"><span data-stu-id="a6522-154">So, at this point, the default columns (all the columns produced by its inputs) are added to the select list by the method AddDefaultColumns.</span></span> <span data-ttu-id="a6522-155">AddDefaultColumns 循环访问 FromExtents 中的每个符号，并为每个符号添加范围内的所有列。</span><span class="sxs-lookup"><span data-stu-id="a6522-155">AddDefaultColumns iterates over the symbols in FromExtents and for each symbol adds all the columns brought in scope.</span></span> <span data-ttu-id="a6522-156">对于简单符号，它将查看符号类型来检索要添加的所有符号属性。</span><span class="sxs-lookup"><span data-stu-id="a6522-156">For a simple symbol, it looks at the symbol type to retrieve all its properties to be added.</span></span> <span data-ttu-id="a6522-157">它还使用列名称填充 AllColumnNames 字典。</span><span class="sxs-lookup"><span data-stu-id="a6522-157">It also populates the AllColumnNames dictionary with the column names.</span></span> <span data-ttu-id="a6522-158">将已完成的 SelectStatement2 追加到 SelectStatement1 的 FROM 子句。</span><span class="sxs-lookup"><span data-stu-id="a6522-158">The completed SelectStatement2 is appended to the FROM clause of SelectStatement1.</span></span>  
  
 <span data-ttu-id="a6522-159">下一步，创建一个新的联接符号来表示 Join2，将该符号标记为嵌套联接，并将其添加到 SelectStatement1 的 AllJoinExtents，然后将其添加到符号表。</span><span class="sxs-lookup"><span data-stu-id="a6522-159">Next, a new join symbol is created to represent Join2, it is marked as a nested join and added to the AllJoinExtents of SelectStatement1 and added to the symbol table.</span></span>  <span data-ttu-id="a6522-160">现在需要处理 Join3 的联接条件 Var(Extent3).OrderID =  Var(Join2).Extent4.OrderID。</span><span class="sxs-lookup"><span data-stu-id="a6522-160">Now the join condition of Join3, Var(Extent3).OrderID =  Var(Join2).Extent4.OrderID, needs to be processed.</span></span> <span data-ttu-id="a6522-161">左侧的处理方式与 Join1 的联接条件的处理方式相似。</span><span class="sxs-lookup"><span data-stu-id="a6522-161">Processing of the left hand side is similar to the join condition of Join1.</span></span> <span data-ttu-id="a6522-162">但右侧的“Var(Join2).Extent4.OrderID”的处理方式有所不同，原因是需要联接平展。</span><span class="sxs-lookup"><span data-stu-id="a6522-162">However, the processing of the right and side "Var(Join2).Extent4.OrderID" is different because join flattening is required.</span></span>  
  
 <span data-ttu-id="a6522-163">下图显示了刚好在处理 DbPropertyExpression "Var(Join2).Extent4.OrderID" 之前的那一刻访问者的状态。</span><span class="sxs-lookup"><span data-stu-id="a6522-163">The next figure shows the state of the visitor right before the DbPropertyExpression "Var(Join2).Extent4.OrderID" is processed.</span></span>  
  
 <span data-ttu-id="a6522-164">下面来看一下如何访问“Var(Join2).Extent4.OrderID”。</span><span class="sxs-lookup"><span data-stu-id="a6522-164">Consider how "Var(Join2).Extent4.OrderID" is visited.</span></span> <span data-ttu-id="a6522-165">首先，访问实例属性“Var(Join2).Extent4”，它是另一个 DbPropertyExpression，并首先访问其实例“Var(Join2)”。</span><span class="sxs-lookup"><span data-stu-id="a6522-165">First, the instance property "Var(Join2).Extent4" is visited, which is another DbPropertyExpression and first visits its instance "Var(Join2)".</span></span> <span data-ttu-id="a6522-166">在符号表的最顶端范围中，“Join2”解析为 <joinSymbol_join2>。</span><span class="sxs-lookup"><span data-stu-id="a6522-166">In the top most scope in the symbol table, "Join2" resolves to <joinSymbol_join2>.</span></span> <span data-ttu-id="a6522-167">在 DbPropertyExpression 的处理“Var(Join2).Extent4”的访问方法中，请注意，当需要访问实例并进行平展时返回的是一个联接符号。</span><span class="sxs-lookup"><span data-stu-id="a6522-167">In the visit method for DbPropertyExpression processing "Var(Join2).Extent4" notice that a join symbol was returned when visiting the instance and flattening is required.</span></span>  
  
 <span data-ttu-id="a6522-168">由于它是一个嵌套联接，因此我们在联接符号的 NameToExtent 字典中查找“Extent4”属性，并将其解析为 <symbol_Extent4>，然后返回一个新的 SymbolPair(<joinSymbol_join2>, <symbol_Extent4>)。</span><span class="sxs-lookup"><span data-stu-id="a6522-168">Since it is a nested join, we look up the property "Extent4" in the NameToExtent dictionary of the join symbol, resolve it to <symbol_Extent4> and return a new SymbolPair(<joinSymbol_join2>, <symbol_Extent4>).</span></span> <span data-ttu-id="a6522-169">由于处理“Var(Join2).Extent4.OrderID”的实例时返回一个符号对，因此，将从返回的符号对 (<symbol_Extent4>) 的 ColumnPart 中解析“OrderID”属性，ColumnPart 具有它表示的范围的列的列表。</span><span class="sxs-lookup"><span data-stu-id="a6522-169">Since a symbol pair is returned from the processing of the instance of "Var(Join2).Extent4.OrderID",  the property "OrderID" is resolved from the ColumnPart of that symbol pair (<symbol_Extent4>), which has a list of the columns of the extent it represents.</span></span> <span data-ttu-id="a6522-170">因此，将“Var(Join2).Extent4.OrderID”解析为 { <joinSymbol_Join2>, ".", <symbol_OrderID>}。</span><span class="sxs-lookup"><span data-stu-id="a6522-170">So, "Var(Join2).Extent4.OrderID" is resolved to { <joinSymbol_Join2>, ".", <symbol_OrderID>}.</span></span>  
  
 <span data-ttu-id="a6522-171">Join4 的联接条件将采用类似方式处理。</span><span class="sxs-lookup"><span data-stu-id="a6522-171">The join condition of Join4 is similarly processed.</span></span> <span data-ttu-id="a6522-172">控制权返回给处理最顶端项目的 VisitInputExpression 方法。</span><span class="sxs-lookup"><span data-stu-id="a6522-172">The control returns to the VisitInputExpression method that processed the top most project.</span></span> <span data-ttu-id="a6522-173">让我们看一下返回的 SelectStatement0 的 FromExtents：输入标识为一个联接，移除原始范围，并替换为一个仅带有联接符号的新范围。</span><span class="sxs-lookup"><span data-stu-id="a6522-173">Looking at the FromExtents of the returned SelectStatement0, the input is identified as a join, and removes the original extents and replaces them with a new extent with just the Join symbol.</span></span> <span data-ttu-id="a6522-174">此外，还更新符号表，然后处理 Project 的投影部分。</span><span class="sxs-lookup"><span data-stu-id="a6522-174">The symbol table is also updated and next the projection part of the Project is processed.</span></span> <span data-ttu-id="a6522-175">如前面所述，对属性进行解析并对联接范围进行平展。</span><span class="sxs-lookup"><span data-stu-id="a6522-175">The resolving of the properties and the flattening of the join extents is as described earlier.</span></span>  
  
 <span data-ttu-id="a6522-176">![Diagram](../../../../../docs/framework/data/adonet/ef/media/9456d6a9-ea2e-40ae-accc-a10e18e28b81.gif "9456d6a9-ea2e-40ae-accc-a10e18e28b81")</span><span class="sxs-lookup"><span data-stu-id="a6522-176">![Diagram](../../../../../docs/framework/data/adonet/ef/media/9456d6a9-ea2e-40ae-accc-a10e18e28b81.gif "9456d6a9-ea2e-40ae-accc-a10e18e28b81")</span></span>  
  
 <span data-ttu-id="a6522-177">最后，生成下面的 SqlSelectStatement：</span><span class="sxs-lookup"><span data-stu-id="a6522-177">Finally, the following SqlSelectStatement is produced:</span></span>  
  
```  
SELECT:   
  "1", " AS ", "[C1]",  
  <symbol_Extent1>, ".", "[ProductID]", " AS ", "[ProductID]",   
  <symbol_Extent1>, ".", "[ProductName]", " AS ", "[ProductName]",  
  <symbol_Extent2>, ".", "[CategoryName]", " AS ", "[CategoryName]",  
  <joinSymbol_Join3>, ".", <symbol_ShipCountry>, " AS ", "[ShipCountry]",   
  <joinSymbol_Join3>, ".", <symbol_ProductID>, " AS ", "[ProductID1]"  
FROM: "[dbo].[Products]", " AS ", <symbol_Extent1>,   
        "LEFT OUTER JOIN ""[dbo].[Categories]", " AS ", <symbol_Extent2>, " ON ", <symbol_Extent1>, ".", "[CategoryID]", " = ", <symbol_Extent2>, ".", "[CategoryID]",   
        "INNER JOIN ",   
        " (", SELECT:   
           <symbol_Extent3>, ".", "[OrderID]", " AS ", <symbol_OrderID>, ",   
              <symbol_Extent3>, ".", "[ProductID]", " AS ", <symbol_ProductID>, ...,  
         <joinSymbol_Join2>, ".", <symbol_OrderID_2>, ", ",   
           <joinSymbol_Join2>, ".", <symbol_CustomerID>, ....,    
        <joinSymbol_Join2>, ".", <symbol_OrderID_3>,   
<joinSymbol_Join2>, ".", <symbol_CustomsDescription>,   
<joinSymbol_Join2>, ".", <symbol_ExciseTax>  
FROM: "[dbo].[OrderDetails]", " AS ", <symbol_Extent3>,   
"LEFT OUTER JOIN ",   
" (", SELECT:   
<symbol_Extent4>, ".", "[OrderID]", " AS ", <symbol_OrderID_2>,   
<symbol_Extent4>, ".", "[CustomerID]", " AS ", <symbol_CustomerID>, ...  
<symbol_Extent5>, ".", "[OrderID]", " AS ", <symbol_OrderID_3>,  
<symbol_Extent5>, ".", "[CustomsDescription]", " AS ", <symbol_CustomsDescription>,  
<symbol_Extent5>, ".", "[ExciseTax]", " AS ", <symbol_ExciseTax>  
FROM: "[dbo].[Orders]", " AS ", <symbol_Extent4>,  
"LEFT OUTER JOIN ", , "[dbo].[InternationalOrders]", " AS ", <symbol_Extent5>,   
" ON ", <symbol_Extent4>, ".", "[OrderID]", " = ", , <symbol_Extent5>, ".", "[OrderID]"  
" )", " AS ", <joinSymbol_Join2>, " ON ", , , <symbol_Extent3>, ".", "[OrderID]", " = ", , <joinSymbol_Join2>, ".", <symbol_OrderID_2>  
" )", " AS ", <joinSymbol_Join3>, " ON ", , , <symbol_Extent1>, ".", "[ProductID]", " = ", , <joinSymbol_Join3>, ".", <symbol_ProductID>  
```  
  
### <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="a6522-178">SQL 生成的第二阶段：生成字符串命令</span><span class="sxs-lookup"><span data-stu-id="a6522-178">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="a6522-179">第二阶段生成符号的实际名称，我们只关注表示名为“OrderID”的列的符号，因为在本例中需要解决冲突。</span><span class="sxs-lookup"><span data-stu-id="a6522-179">The second phase produces actual names for the symbols, and we only focus on the symbols representing columns named "OrderID", as in this case a conflict needs to be resolved.</span></span> <span data-ttu-id="a6522-180">SqlSelectStatement 中突出显示了这些符号。</span><span class="sxs-lookup"><span data-stu-id="a6522-180">These are highlighted in the SqlSelectStatement.</span></span> <span data-ttu-id="a6522-181">请注意，图中使用的后缀仅强调这些符号是不同的实例，而不表示任何新的名称，因为在此阶段还未指派它们的最终名称，这些最终名称很可能与原始名称不同。</span><span class="sxs-lookup"><span data-stu-id="a6522-181">Note that the suffixes used in the figure are only to emphasize that these are different instances, not to represent any new names, as at this stage their final names (possibly different form the original names) have not been assigned yet.</span></span>  
  
 <span data-ttu-id="a6522-182">查找到的需要重命名的第一个符号是 <symbol_OrderID>。</span><span class="sxs-lookup"><span data-stu-id="a6522-182">The first symbol found that needs to be renamed is <symbol_OrderID>.</span></span> <span data-ttu-id="a6522-183">为它指派的新名称为“OrderID1”，标记 1 表示为“OrderID”使用的最后一个后缀，该符号标记为不需要重命名。</span><span class="sxs-lookup"><span data-stu-id="a6522-183">Its new name is assigned as "OrderID1", 1 is marked as the last used suffix for "OrderID" and the symbol is marked as not needing renaming.</span></span> <span data-ttu-id="a6522-184">接下来，找到第一个 <symbol_OrderID_2>。</span><span class="sxs-lookup"><span data-stu-id="a6522-184">Next, the first usage of <symbol_OrderID_2> is found.</span></span> <span data-ttu-id="a6522-185">将它重命名为使用下一个可用的后缀“OrderID2”，同样将其标记为不需要重命名，以便在下一次使用它时不需要再进行重命名。</span><span class="sxs-lookup"><span data-stu-id="a6522-185">It is renamed to use the next available suffix ("OrderID2") and again marked as not needing renaming, so that next time it is used it does not get renamed.</span></span> <span data-ttu-id="a6522-186">对于 <symbol_OrderID_3> 也执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="a6522-186">This is done for <symbol_OrderID_3> too.</span></span>  
  
 <span data-ttu-id="a6522-187">在第二阶段结束时，将生成最后的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="a6522-187">At the end of the second phase, the final SQL statement is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6522-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6522-188">See Also</span></span>  
 [<span data-ttu-id="a6522-189">示例提供程序中的 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="a6522-189">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)
