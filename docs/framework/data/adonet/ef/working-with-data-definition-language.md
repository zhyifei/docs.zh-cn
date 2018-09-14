---
title: 使用数据定义语言
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: 25d7f49644996d87ddb5d191dc313916c0ca6fbb
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513926"
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="12cad-102">使用数据定义语言</span><span class="sxs-lookup"><span data-stu-id="12cad-102">Working with Data Definition Language</span></span>
<span data-ttu-id="12cad-103">从开始[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]版本 4 中，[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]支持数据定义语言 (DDL)。</span><span class="sxs-lookup"><span data-stu-id="12cad-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="12cad-104">这样，您将能够基于连接字符串和存储元数据 (SSDL) 模型创建或删除数据库实例。</span><span class="sxs-lookup"><span data-stu-id="12cad-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="12cad-105"><xref:System.Data.Objects.ObjectContext> 的以下方法使用连接字符串和 SSDL 内容来完成以下操作：创建或删除数据库，检查数据库是否存在，以及查看生成的 DDL 脚本：</span><span class="sxs-lookup"><span data-stu-id="12cad-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="12cad-106">假定有足够的权限可执行 DDL 命令。</span><span class="sxs-lookup"><span data-stu-id="12cad-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="12cad-107">以上列出的方法将大部分工作都委托给基础 ADO.NET 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="12cad-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="12cad-108">该提供程序负责确保用于生成数据库对象的命名约定与用于查询和更新的约定保持一致。</span><span class="sxs-lookup"><span data-stu-id="12cad-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="12cad-109">下面的示例演示如何基于现有模型生成数据库。</span><span class="sxs-lookup"><span data-stu-id="12cad-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="12cad-110">它还将新的实体对象添加到对象上下文中，然后将该对象保存到数据库中。</span><span class="sxs-lookup"><span data-stu-id="12cad-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="12cad-111">过程</span><span class="sxs-lookup"><span data-stu-id="12cad-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="12cad-112">基于现有模型定义数据库</span><span class="sxs-lookup"><span data-stu-id="12cad-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="12cad-113">创建控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="12cad-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="12cad-114">向应用程序中添加现有模型。</span><span class="sxs-lookup"><span data-stu-id="12cad-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="12cad-115">添加名为一个空模型`SchoolModel`。</span><span class="sxs-lookup"><span data-stu-id="12cad-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="12cad-116">若要创建一个空模型，请参阅[如何： 创建新的.edmx 文件](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)主题。</span><span class="sxs-lookup"><span data-stu-id="12cad-116">To create an empty model, see the [How to: Create a New .edmx File](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="12cad-117">将 SchoolModel.edmx 文件添加到您的项目中。</span><span class="sxs-lookup"><span data-stu-id="12cad-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="12cad-118">复制概念、 存储和映射中的 School 模型的内容[School 模型](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)主题。</span><span class="sxs-lookup"><span data-stu-id="12cad-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="12cad-119">打开 SchoolModel.edmx 文件并将内容粘贴在 `edmx:Runtime` 标记中。</span><span class="sxs-lookup"><span data-stu-id="12cad-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="12cad-120">将以下代码添加到主函数中。</span><span class="sxs-lookup"><span data-stu-id="12cad-120">Add the following code to your main function.</span></span> <span data-ttu-id="12cad-121">此类代码将连接字符串初始化为数据库服务器，查看 DDL 脚本，创建数据库，将新实体添加到上下文，并将更改保存到数据库。</span><span class="sxs-lookup"><span data-stu-id="12cad-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
