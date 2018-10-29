---
title: 如何：在 Visual Basic 或 C# 中生成对象模型
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 21266ca2d1230a1afc903734d1b4c53b259e50e1
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200922"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="96c14-102">如何：在 Visual Basic 或 C# 中生成对象模型</span><span class="sxs-lookup"><span data-stu-id="96c14-102">How to: Generate the Object Model in Visual Basic or C#</span></span> #
<span data-ttu-id="96c14-103">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，采用您自己的编程语言的对象模型映射到关系数据库。</span><span class="sxs-lookup"><span data-stu-id="96c14-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="96c14-104">两个工具是可用于自动生成 Visual Basic 或C#从现有数据库的元数据模型。</span><span class="sxs-lookup"><span data-stu-id="96c14-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
-   <span data-ttu-id="96c14-105">如果使用的 Visual Studio，则可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]生成对象模型。</span><span class="sxs-lookup"><span data-stu-id="96c14-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to generate an object model.</span></span> <span data-ttu-id="96c14-106">[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]提供了丰富的用户界面来帮助您生成[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]对象模型。</span><span class="sxs-lookup"><span data-stu-id="96c14-106">The [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="96c14-107">有关详细信息，请参阅[Linq to SQL 工具在 Visual Studio 中](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)。</span><span class="sxs-lookup"><span data-stu-id="96c14-107">For more information see, [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
-   <span data-ttu-id="96c14-108">SQLMetal 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="96c14-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="96c14-109">有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="96c14-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96c14-110">如果你没有现有数据库且希望利用对象模型创建一个，则可以使用代码编辑器和 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 来创建对象模型。</span><span class="sxs-lookup"><span data-stu-id="96c14-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="96c14-111">有关详细信息，请参阅[如何： 动态创建数据库](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)。</span><span class="sxs-lookup"><span data-stu-id="96c14-111">For more information, see [How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="96c14-112">文档[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]示例展示了如何生成 Visual Basic 或C#通过使用对象模型[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="96c14-112">Documentation for the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides examples of how to generate a Visual Basic or C# object model by using the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].</span></span> <span data-ttu-id="96c14-113">以下信息提供了有关如何使用 SQLMetal 命令行工具的示例。</span><span class="sxs-lookup"><span data-stu-id="96c14-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="96c14-114">有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="96c14-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96c14-115">示例</span><span class="sxs-lookup"><span data-stu-id="96c14-115">Example</span></span>  
 <span data-ttu-id="96c14-116">在下面的示例显示的 SQLMetal 命令行生成 Visual Basic 代码作为 Northwind 示例数据库的基于属性的对象模型。</span><span class="sxs-lookup"><span data-stu-id="96c14-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="96c14-117">还呈现了存储过程和函数。</span><span class="sxs-lookup"><span data-stu-id="96c14-117">Stored procedures and functions are also rendered.</span></span>  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="96c14-118">示例</span><span class="sxs-lookup"><span data-stu-id="96c14-118">Example</span></span>  
 <span data-ttu-id="96c14-119">下面的示例中显示的 SQLMetal 命令行会生成 C# 代码作为 Northwind 示例数据库的基于属性的对象模型。</span><span class="sxs-lookup"><span data-stu-id="96c14-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="96c14-120">还呈现了存储过程和函数，并自动将表名变为复数形式。</span><span class="sxs-lookup"><span data-stu-id="96c14-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="96c14-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="96c14-121">See Also</span></span>  
 [<span data-ttu-id="96c14-122">编程指南</span><span class="sxs-lookup"><span data-stu-id="96c14-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [<span data-ttu-id="96c14-123">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="96c14-123">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="96c14-124">通过演练学习</span><span class="sxs-lookup"><span data-stu-id="96c14-124">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="96c14-125">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="96c14-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [<span data-ttu-id="96c14-126">基于特性的映射</span><span class="sxs-lookup"><span data-stu-id="96c14-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="96c14-127">SqlMetal.exe（代码生成工具）</span><span class="sxs-lookup"><span data-stu-id="96c14-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="96c14-128">外部映射</span><span class="sxs-lookup"><span data-stu-id="96c14-128">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [<span data-ttu-id="96c14-129">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="96c14-129">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="96c14-130">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="96c14-130">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
