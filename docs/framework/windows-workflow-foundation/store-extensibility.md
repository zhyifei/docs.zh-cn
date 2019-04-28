---
title: 存储扩展性
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: 46c1ea40925a5c79180171da9a705d7e6b7c8b89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641601"
---
# <a name="store-extensibility"></a><span data-ttu-id="e7939-102">存储扩展性</span><span class="sxs-lookup"><span data-stu-id="e7939-102">Store Extensibility</span></span>

<span data-ttu-id="e7939-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 允许用户提升自定义的特定于应用程序的属性，这些属性可用于查询持久性数据库中的实例。</span><span class="sxs-lookup"><span data-stu-id="e7939-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> allows users to promote custom, application-specific properties that can be used to query for instances in the persistence database.</span></span> <span data-ttu-id="e7939-104">提升属性的操作将使属性值可用在数据库的特殊视图中。</span><span class="sxs-lookup"><span data-stu-id="e7939-104">The act of promoting a property causes the value to be available within a special view in the database.</span></span> <span data-ttu-id="e7939-105">这些提升的属性（可用于用户查询的属性）可以是简单的类型，如 Int64、Guid、String 和 DateTime，也可以是序列化的二进制类型 (byte[])。</span><span class="sxs-lookup"><span data-stu-id="e7939-105">These promoted properties (properties that can be used in user queries) can be of simple types such as Int64, Guid, String, and DateTime or of a serialized binary type (byte[]).</span></span>

<span data-ttu-id="e7939-106"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 类具有 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> 方法，可以使用该方法将某个属性提升为可以在查询中使用的属性。</span><span class="sxs-lookup"><span data-stu-id="e7939-106">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class has the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> method that you can use to promote a property as a property that can be used in queries.</span></span> <span data-ttu-id="e7939-107">以下示例是存储扩展性的一个端对端示例。</span><span class="sxs-lookup"><span data-stu-id="e7939-107">The following example is an end-to-end example of store extensibility.</span></span>

1. <span data-ttu-id="e7939-108">在此示例方案中，文档处理 (DP) 应用程序具有多个工作流，每个工作流都使用自定义的活动进行文档处理。</span><span class="sxs-lookup"><span data-stu-id="e7939-108">In this example scenario, a document processing (DP) application has workflows, each of which uses custom activities for document processing.</span></span> <span data-ttu-id="e7939-109">这些工作流具有一组状态变量，最终用户需要看到这些变量。</span><span class="sxs-lookup"><span data-stu-id="e7939-109">These workflows have a set of state variables that need to be made visible to the end user.</span></span> <span data-ttu-id="e7939-110">为了实现此目的，DP 应用程序提供了一个类型为 <xref:System.Activities.Persistence.PersistenceParticipant> 的实例扩展，活动使用该实例扩展来提供状态变量。</span><span class="sxs-lookup"><span data-stu-id="e7939-110">To achieve this, the DP application provides an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span>

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        public string DocumentId;
        public string ApprovalStatus;
        public string UserName;
        public DateTime LastUpdateTime;
    }
    ```

2. <span data-ttu-id="e7939-111">然后，将新的扩展添加到主机。</span><span class="sxs-lookup"><span data-stu-id="e7939-111">The new extension is then added to the host.</span></span>

    ```csharp
    static Activity workflow = CreateWorkflow();
    WorkflowApplication application = new WorkflowApplication(workflow);
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();
    application.Extensions.Add(documentStatusExtension);
    ```

     <span data-ttu-id="e7939-112">有关添加自定义持久性参与者的更多详细信息，请参阅[持久性参与者](persistence-participants.md)示例。</span><span class="sxs-lookup"><span data-stu-id="e7939-112">For more details about adding a custom persistence participant, see the [Persistence Participants](persistence-participants.md) sample.</span></span>

3. <span data-ttu-id="e7939-113">DP 应用程序中的自定义活动填充中的各种状态字段**Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="e7939-113">The custom activities in the DP application populate various status fields in the **Execute** method.</span></span>

    ```csharp
    public override void Execute(CodeActivityContext context)
    {
        // ...
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = "Approved";
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();
        // ...
    }
    ```

4. <span data-ttu-id="e7939-114">当工作流实例达到持久点时， **CollectValues**方法**DocumentStatusExtension**持久性参与者将这些属性保存到持久性数据集合。</span><span class="sxs-lookup"><span data-stu-id="e7939-114">When a workflow instance reaches a persistence point, the **CollectValues** method of the **DocumentStatusExtension** persistence participant saves these properties into the persistence data collection.</span></span>

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        const XNamespace xNS = XNamespace.Get("http://contoso.com/DocumentStatus");

        protected override void CollectValues(out IDictionary<XName, object> readWriteValues, out IDictionary<XName, object> writeOnlyValues)
        {
            readWriteValues = new Dictionary<XName, object>();
            readWriteValues.Add(xNS.GetName("UserName"), this.UserName);
            readWriteValues.Add(xNS.GetName("ApprovalStatus"), this.ApprovalStatus);
            readWriteValues.Add(xNS.GetName("DocumentId"), this.DocumentId);
            readWriteValues.Add(xNS.GetName("LastModifiedTime"), this.LastUpdateTime);

            writeOnlyValues = null;
        }
        // ...
    }
    ```

    > [!NOTE]
    > <span data-ttu-id="e7939-115">所有这些属性传递给**SqlWorkflowInstanceStore**由持久性框架通过**SaveWorkflowCommand.InstanceData**集合。</span><span class="sxs-lookup"><span data-stu-id="e7939-115">All these properties are passed to **SqlWorkflowInstanceStore** by the persistence framework through the **SaveWorkflowCommand.InstanceData** collection.</span></span>

5. <span data-ttu-id="e7939-116">DP 应用程序初始化 SQL 工作流实例存储并调用**Promote**方法来提升此数据。</span><span class="sxs-lookup"><span data-stu-id="e7939-116">The DP application initializes the SQL Workflow Instance Store and invokes the **Promote** method to promote this data.</span></span>

    ```csharp
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);

    List<XName> variantProperties = new List<XName>()
    {
        xNS.GetName("UserName"),
        xNS.GetName("ApprovalStatus"),
        xNS.GetName("DocumentId"),
        xNS.GetName("LastModifiedTime")
    };

    store.Promote("DocumentStatus", variantProperties, null);
    ```

    <span data-ttu-id="e7939-117">根据此提升信息， **SqlWorkflowInstanceStore**将数据属性放置中的列[InstancePromotedProperties](#InstancePromotedProperties)视图。</span><span class="sxs-lookup"><span data-stu-id="e7939-117">Based on this promotion information, **SqlWorkflowInstanceStore** places the data properties in the columns of the [InstancePromotedProperties](#InstancePromotedProperties) view.</span></span>

6. <span data-ttu-id="e7939-118">为了从提升表中查询某个数据子集，DP 应用程序在提升视图之上添加一个自定义视图。</span><span class="sxs-lookup"><span data-stu-id="e7939-118">To query a subset of the data from the promotion table, the DP application adds a customized view on top of the promotion view.</span></span>

    ```sql
    create view [dbo].[DocumentStatus] with schemabinding
    as
        select  P.[InstanceId] as [InstanceId],
            P.Value1 as [UserName],
            P.Value2 as [ApprovalStatus],
            P.Value3 as [DocumentId],
            P.Value4 as [LastUpdatedTime]
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P
    where P.PromotionName = N'DocumentStatus'
    go
    ```

## <a name="InstancePromotedProperties"></a> <span data-ttu-id="e7939-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span><span class="sxs-lookup"><span data-stu-id="e7939-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span></span>

|<span data-ttu-id="e7939-120">列名</span><span class="sxs-lookup"><span data-stu-id="e7939-120">Column Name</span></span>|<span data-ttu-id="e7939-121">列名称</span><span class="sxs-lookup"><span data-stu-id="e7939-121">Column Type</span></span>|<span data-ttu-id="e7939-122">描述</span><span class="sxs-lookup"><span data-stu-id="e7939-122">Description</span></span>|
|-----------------|-----------------|-----------------|
|<span data-ttu-id="e7939-123">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e7939-123">InstanceId</span></span>|<span data-ttu-id="e7939-124">GUID</span><span class="sxs-lookup"><span data-stu-id="e7939-124">GUID</span></span>|<span data-ttu-id="e7939-125">此提升所属的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="e7939-125">The workflow instance that this promotion belongs to.</span></span>|
|<span data-ttu-id="e7939-126">PromotionName</span><span class="sxs-lookup"><span data-stu-id="e7939-126">PromotionName</span></span>|<span data-ttu-id="e7939-127">nvarchar(400)</span><span class="sxs-lookup"><span data-stu-id="e7939-127">nvarchar(400)</span></span>|<span data-ttu-id="e7939-128">提升本身的名称。</span><span class="sxs-lookup"><span data-stu-id="e7939-128">The name of the promotion itself.</span></span>|
|<span data-ttu-id="e7939-129">Value1、Value2、Value3、..、Value32</span><span class="sxs-lookup"><span data-stu-id="e7939-129">Value1, Value2, Value3,..,Value32</span></span>|<span data-ttu-id="e7939-130">sql_variant</span><span class="sxs-lookup"><span data-stu-id="e7939-130">sql_variant</span></span>|<span data-ttu-id="e7939-131">已提升属性本身的值。</span><span class="sxs-lookup"><span data-stu-id="e7939-131">The value of the promoted property itself.</span></span> <span data-ttu-id="e7939-132">除了长度超过 8000 个字节的二进制 Blob 和字符串之外，多数 SQL 基元数据类型都可适合 sql_variant。</span><span class="sxs-lookup"><span data-stu-id="e7939-132">Most SQL primitive data types except binary blobs and strings over 8000 bytes in length can fit in sql_variant.</span></span>|
|<span data-ttu-id="e7939-133">Value33、Value34、Value35、…、Value64</span><span class="sxs-lookup"><span data-stu-id="e7939-133">Value33, Value34, Value35, …, Value64</span></span>|<span data-ttu-id="e7939-134">varbinary(max)</span><span class="sxs-lookup"><span data-stu-id="e7939-134">varbinary(max)</span></span>|<span data-ttu-id="e7939-135">显式声明为 varbinary(max) 的已提升属性的值。</span><span class="sxs-lookup"><span data-stu-id="e7939-135">The value of promoted properties that are explicitly declared as varbinary(max).</span></span>|
