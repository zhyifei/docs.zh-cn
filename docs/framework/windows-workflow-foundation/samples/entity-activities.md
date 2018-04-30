---
title: 实体活动
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff7e505f6e2040e847b711030d310a70ede65413
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="entity-activities"></a><span data-ttu-id="f3099-102">实体活动</span><span class="sxs-lookup"><span data-stu-id="f3099-102">Entity Activities</span></span>
<span data-ttu-id="f3099-103">此示例演示如何使用 ADO.NET 实体框架 Windows Workflow Foundation 来简化数据访问。</span><span class="sxs-lookup"><span data-stu-id="f3099-103">This sample shows how to use the ADO.NET Entity Framework with Windows Workflow Foundation to simplify data access.</span></span>  
  
 <span data-ttu-id="f3099-104">ADO.NET 实体框架使开发人员可以处理以下形式的数据：特定于域的对象、属性和关系（例如客户、订单、订单详细信息以及这些实体之间的关系）。</span><span class="sxs-lookup"><span data-stu-id="f3099-104">The ADO.NET Entity Framework enables developers to work with data in the form of domain-specific objects, properties and relationships such as Customers, Orders, Order Details and the relationships between these entities.</span></span> <span data-ttu-id="f3099-105">ADO.NET 实体框架通过提供一个抽象级别以便能够针对一个概念应用程序模型编程（而不是针对一个关系存储架构直接编程）来做到这一点。</span><span class="sxs-lookup"><span data-stu-id="f3099-105">The ADO.NET Entity Framework does this by providing a level of abstraction that enables programming against a conceptual application model instead of programming directly against a relational storage schema.</span></span> <span data-ttu-id="f3099-106">ADO.NET 实体框架，请参阅有关详细信息[ADO.NET 实体框架](http://go.microsoft.com/fwlink/?LinkId=165549)。</span><span class="sxs-lookup"><span data-stu-id="f3099-106">For more information about the ADO.NET Entity Framework see [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="f3099-107">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="f3099-107">Sample details</span></span>  
 <span data-ttu-id="f3099-108">此示例使用 `Northwind` 数据库，并包含用于创建和移除 `Northwind` 数据库的脚本（Setup.cmd 和 Cleanup.cmd）。</span><span class="sxs-lookup"><span data-stu-id="f3099-108">This sample uses the `Northwind` database and includes scripts for creating and removing the `Northwind` database (Setup.cmd and Cleanup.cmd).</span></span> <span data-ttu-id="f3099-109">此示例中的项目包含一个基于 `Northwind` 数据库的实体数据模型。</span><span class="sxs-lookup"><span data-stu-id="f3099-109">The projects in this sample include an Entity Data Model based on the `Northwind` database.</span></span> <span data-ttu-id="f3099-110">您可以通过打开包含在项目中的 `Northwind.edmx` 文件找到此模型。</span><span class="sxs-lookup"><span data-stu-id="f3099-110">You can find the model by opening the `Northwind.edmx` file that is included in the project.</span></span> <span data-ttu-id="f3099-111">此模型用于定义可使用 ADO.NET 实体框架访问的对象的形状。</span><span class="sxs-lookup"><span data-stu-id="f3099-111">This is the model that defines the shape of the objects that can be accessed using the ADO.NET Entity Framework.</span></span>  
  
 <span data-ttu-id="f3099-112">此示例中包括以下活动：</span><span class="sxs-lookup"><span data-stu-id="f3099-112">The following activities are included in this sample:</span></span>  
  
-   <span data-ttu-id="f3099-113">`EntitySQLQuery`：`EntitySQLQuery` 活动允许您基于 Entity SQL 查询字符串从数据库中检索对象。</span><span class="sxs-lookup"><span data-stu-id="f3099-113">`EntitySQLQuery`: The `EntitySQLQuery` activity allows you to retrieve objects from the database based on an Entity SQL query string.</span></span> <span data-ttu-id="f3099-114">Entity SQL 是一种与 SQL 相似的、独立于存储的语言，它允许您基于概念模型以及属于该模型或域的一部分的实体来指定查询。</span><span class="sxs-lookup"><span data-stu-id="f3099-114">Entity SQL is a store independent language that is similar to SQL and it allows you to specify queries based on the conceptual model and the entities that are a part of the model or domain.</span></span> <span data-ttu-id="f3099-115">有关实体 SQL 语言的详细信息，请参阅[Entity SQL 语言](http://go.microsoft.com/fwlink/?LinkId=165646)。</span><span class="sxs-lookup"><span data-stu-id="f3099-115">For more information about Entity SQL Language, see [Entity SQL Language](http://go.microsoft.com/fwlink/?LinkId=165646).</span></span>  
  
-   <span data-ttu-id="f3099-116">`EntityLinqQuery`：此活动允许您基于 LINQ 查询或谓词从数据库中检索对象。</span><span class="sxs-lookup"><span data-stu-id="f3099-116">`EntityLinqQuery`: This activity allows you to retrieve objects from the database based on a LINQ query or predicate.</span></span>  
  
-   <span data-ttu-id="f3099-117">`EntityAdd`：`EntityAdd` 活动允许您在数据库中添加一个实体或一个实体集合。</span><span class="sxs-lookup"><span data-stu-id="f3099-117">`EntityAdd`: The `EntityAdd` activity allows you to add an entity or a collection of entities to the database.</span></span>  
  
-   <span data-ttu-id="f3099-118">`EntityDelete`：`EntityDelete` 活动允许您从数据库中删除一个实体或一个实体集合。</span><span class="sxs-lookup"><span data-stu-id="f3099-118">`EntityDelete`: The `EntityDelete` activity allows you to delete an entity or a collection of entities from the database.</span></span>  
  
-   <span data-ttu-id="f3099-119">`ObjectContextScope`：前面提及的活动只能在一个包含 `ObjectContextScope` 活动实例中使用。</span><span class="sxs-lookup"><span data-stu-id="f3099-119">`ObjectContextScope`: The previously mentioned activities can only be used within a containing `ObjectContextScope` activity instance.</span></span> <span data-ttu-id="f3099-120">`ObjectContextScope` 活动设置与数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="f3099-120">The `ObjectContextScope` activity sets up the connection to the database.</span></span> <span data-ttu-id="f3099-121">该活动要求一个连接字符串（既可以传入此字符串，也可以使用配置文件设置检索此字符串）。</span><span class="sxs-lookup"><span data-stu-id="f3099-121">It requires a connection string (that is either passed in or retrieved using a configuration file setting).</span></span> <span data-ttu-id="f3099-122">`ObjectContextScope` 活动可以简化对实体执行一组相关操作的任务。</span><span class="sxs-lookup"><span data-stu-id="f3099-122">The `ObjectContextScope` activity makes it easy to perform a group of related operations on entities.</span></span> <span data-ttu-id="f3099-123">因为此范围维护一个活动连接, 所以它是一个非持久范围。</span><span class="sxs-lookup"><span data-stu-id="f3099-123">Because this scope maintains an active connection, it is a No Persist scope.</span></span> <span data-ttu-id="f3099-124">此外，当 `ObjectContextScope` 活动退出时，对在该范围内使用实体活动检索到的对象所做的任何更改将会自动保存回数据库，而无需执行显式的或后续的操作来将对象保存到数据库。</span><span class="sxs-lookup"><span data-stu-id="f3099-124">In addition, when the `ObjectContextScope` activity exits, any changes that are made to objects retrieved using Entity Activities within that scope automatically get persisted back to the database, and no explicit or subsequent action is required to save objects back to the database.</span></span>  
  
## <a name="using-the-entity-activities"></a><span data-ttu-id="f3099-125">使用实体活动</span><span class="sxs-lookup"><span data-stu-id="f3099-125">Using the entity activities</span></span>  
 <span data-ttu-id="f3099-126">以下代码段演示如何使用此实例中提供的实体活动。</span><span class="sxs-lookup"><span data-stu-id="f3099-126">The following code snippets demonstrate how to use the entity activities presented in this sample.</span></span>  
  
### <a name="entitysql"></a><span data-ttu-id="f3099-127">EntitySql</span><span class="sxs-lookup"><span data-stu-id="f3099-127">EntitySql</span></span>  
 <span data-ttu-id="f3099-128">以下代码段演示如何查询所有位于伦敦的客户并按名称排序，并演示如何循环访问客户列表。</span><span class="sxs-lookup"><span data-stu-id="f3099-128">The code snippet below shows how to query all customers in London sorted by name and how to iterate through the list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>();  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>();  
  
// create and return the workflow  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
        {  
            Activities =   
                {               
                    new WriteLine { Text = "Executing query" },                            
                    // query for all customers that are in london   
                    new EntitySqlQuery<Customer>  
                    {  
                        EntitySql =  @"SELECT VALUE Customer   
                                        FROM NorthwindEntities.Customers AS Customer   
                                        WHERE Customer.City = 'London'   
                                        ORDER BY Customer.ContactName",  
                        Result = londonCustomers  
                    },  
  
                    // iterate through the list of customers and display them   
                    new ForEach<Customer>  
                    {                                      
                        Values = londonCustomers,  
                        Body = new ActivityAction<Customer>  
                        {  
                            Argument = iterationVariable,  
                            Handler = new WriteLine   
                            {   
                                  Text = new InArgument<String>(e =>    
                                              iterationVariable.Get(e).ContactName)   
                            }  
                        }  
                    }  
                }  
        }                 
};     
```  
  
### <a name="entitylinqquery"></a><span data-ttu-id="f3099-129">EntityLinqQuery</span><span class="sxs-lookup"><span data-stu-id="f3099-129">EntityLinqQuery</span></span>  
 <span data-ttu-id="f3099-130">以下代码段演示如何查询所有位于伦敦的客户，并演示如何循环生成的访问客户列表。</span><span class="sxs-lookup"><span data-stu-id="f3099-130">The code snippet below shows how to query all customers in London and how to iterate through the resulting list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>() { Name = "LondonCustomers" };  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>() { Name = "iterationVariable" };  
  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // return all the customers that match with the provided Linq predicate  
            new EntityLinqQuery<Customer>  
            {   
                Predicate = new LambdaValue<Func<Customer, bool>>(  
                          ctx => new Func<Customer, bool>(c => c.City.Equals("London"))),                              
                Result = londonCustomers  
            },  
  
            // iterate through the list of customers and display in the console  
            new ForEach<Customer>  
            {                                      
                Values = londonCustomers,  
                Body = new ActivityAction<Customer>  
                {  
                    Argument = iterationVariable,  
                    Handler = new WriteLine   
                    {   
                        Text = new InArgument<String>(e =>   
                                      iterationVariable.Get(e).ContactName)   
                    }  
                }  
            }  
        }  
    }  
};  
```  
  
### <a name="entityadd"></a><span data-ttu-id="f3099-131">EntityAdd</span><span class="sxs-lookup"><span data-stu-id="f3099-131">EntityAdd</span></span>  
 <span data-ttu-id="f3099-132">以下代码段演示如何将一个 OrderDetail 记录添加到一个现有的 Order 中。</span><span class="sxs-lookup"><span data-stu-id="f3099-132">The code snippet below shows how to add an OrderDetail record to an existing Order.</span></span>  
  
```  
Variable<IEnumerable<Order>> orders = new Variable<IEnumerable<Order>>();  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();  
Variable<Order> order = new Variable<Order>();  
Variable<OrderDetail> orderDetail = new Variable<OrderDetail>();              
  
return new ObjectContextScope  
{  
    Variables = { order, orders, orderDetail, orderDetails },  
    ContainerName = "NorthwindEntities",  
    ConnectionString = new InArgument<string>(connStr),                  
    Body = new Sequence  
    {                      
        Activities =   
        {                            
           // get the order where we want to add the detail  
           new EntitySqlQuery<Order>  
           {  
               EntitySql =    
                    @"SELECT VALUE [Order]  
                      FROM NorthwindEntities.Orders as [Order]  
                      WHERE Order.OrderID == 10249",  
               Result = orders  
           },  
  
           // store the order in a variable  
           new Assign<Order>   
           {  
               To = new OutArgument<Order>(order),  
               Value = new InArgument<Order>(c => orders.Get(c).First<Order>())  
           },  
  
           // add the detail to the order  
           new EntityAdd<OrderDetail>  
           {  
               Entity = new InArgument<OrderDetail>(c =>   
                                         new OrderDetail {   
                                                  OrderID=10249, ProductID=11,   
                                                  Quantity=1, UnitPrice = 15,   
                                                  Discount = 0, Order = order.Get(c) })  
           }  
        }  
    }  
};  
```  
  
### <a name="entitydelete"></a><span data-ttu-id="f3099-133">EntityDelete</span><span class="sxs-lookup"><span data-stu-id="f3099-133">EntityDelete</span></span>  
 <span data-ttu-id="f3099-134">以下代码段演示如何在一个 Order 中删除一个现有的 OrderDetail 记录（如果它存在）。</span><span class="sxs-lookup"><span data-stu-id="f3099-134">The code snippet below shows how to delete an existing OrderDetail record in an Order (if it exists).</span></span>  
  
```  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();              
  
return new ObjectContextScope  
{  
    Variables = { orderDetails },  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // find the entitiy to be deleted (order detail for product 11 in order 10249)  
            new EntitySqlQuery<OrderDetail>  
            {  
                EntitySql = @"SELECT VALUE OrderDetail  
                                FROM NorthwindEntities.OrderDetails as OrderDetail  
                               WHERE OrderDetail.OrderID == 10249   
                                 AND OrderDetail.ProductID == 11",  
                Result = orderDetails  
            },  
  
            // if the order detail is found, delete it, otherwise, display a message  
            new If  
            {  
                Condition = new InArgument<bool>(c=>orderDetails.Get(c).Count() > 0),  
                Then = new Sequence  
                {   
                    Activities =   
                    {                                      
                        new EntityDelete<OrderDetail>  
                        {  
                            Entity = new InArgument<OrderDetail>(c =>   
                                              orderDetails.Get(c).First<OrderDetail>())  
                        },  
                    }  
                },                              
                Else = new WriteLine { Text = "Order Detail for Deleting not found" }                              
            }                                                  
        }  
    }  
};  
```  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="f3099-135">使用此示例</span><span class="sxs-lookup"><span data-stu-id="f3099-135">To use this sample</span></span>  
 <span data-ttu-id="f3099-136">运行此示例之前，必须在本地 SQL Server Express 实例中创建 `Northwind` 数据库。</span><span class="sxs-lookup"><span data-stu-id="f3099-136">You must create the `Northwind` database in your local SQL server Express instance before running this sample.</span></span>  
  
#### <a name="to-set-up-the-northwind-database"></a><span data-ttu-id="f3099-137">设置 Northwind 数据库</span><span class="sxs-lookup"><span data-stu-id="f3099-137">To set up the Northwind database</span></span>  
  
1.  <span data-ttu-id="f3099-138">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="f3099-138">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="f3099-139">在新的命令提示窗口中，定位到 EntityActivities\CS 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f3099-139">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="f3099-140">类型`setup.cmd`，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="f3099-140">Type `setup.cmd` and press ENTER.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="f3099-141">运行示例</span><span class="sxs-lookup"><span data-stu-id="f3099-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="f3099-142">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 EntityActivities.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="f3099-142">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EntityActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f3099-143">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="f3099-143">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f3099-144">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="f3099-144">To run the solution, press CTRL+F5.</span></span>  
  
 <span data-ttu-id="f3099-145">运行此示例之后，您可能需要移除 `Northwind` 数据库。</span><span class="sxs-lookup"><span data-stu-id="f3099-145">After running this sample, you may want to remove the `Northwind` database.</span></span>  
  
#### <a name="to-uninstall-the-northwind-database"></a><span data-ttu-id="f3099-146">卸载 Northwind 数据库</span><span class="sxs-lookup"><span data-stu-id="f3099-146">To uninstall the Northwind database</span></span>  
  
1.  <span data-ttu-id="f3099-147">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="f3099-147">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="f3099-148">在新的命令提示窗口中，定位到 EntityActivities\CS 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f3099-148">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="f3099-149">类型`cleanup.cmd`，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="f3099-149">Type `cleanup.cmd` and press ENTER.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f3099-150">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f3099-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f3099-151">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f3099-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f3099-152">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="f3099-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f3099-153">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f3099-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`