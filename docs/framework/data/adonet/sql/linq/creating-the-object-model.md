---
title: 创建对象模型
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8686b46545699ab8c07b5d3b5f3ea26080261036
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="creating-the-object-model"></a><span data-ttu-id="5a863-102">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="5a863-102">Creating the Object Model</span></span>
<span data-ttu-id="5a863-103">您可以从现有数据库中创建对象模型并以该模型的默认状态使用它。</span><span class="sxs-lookup"><span data-stu-id="5a863-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="5a863-104">您还可以自定义该模型的许多方面及其行为。</span><span class="sxs-lookup"><span data-stu-id="5a863-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="5a863-105">如果你使用的 Visual Studio，则可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来创建对象模型。</span><span class="sxs-lookup"><span data-stu-id="5a863-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a863-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="5a863-106">In This Section</span></span>  
 [<span data-ttu-id="5a863-107">如何：在 Visual Basic 或 C# 中生成对象模型</span><span class="sxs-lookup"><span data-stu-id="5a863-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="5a863-108">介绍如何使用 SQLMetal 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="5a863-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="5a863-109">也提供了链接到[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]对于 Visual Studio 用户</span><span class="sxs-lookup"><span data-stu-id="5a863-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for Visual Studio users</span></span>  
  
 [<span data-ttu-id="5a863-110">如何：将对象模型作为外部文件生成</span><span class="sxs-lookup"><span data-stu-id="5a863-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="5a863-111">介绍如何生成外部映射文件，而不是使用基于属性的映射。</span><span class="sxs-lookup"><span data-stu-id="5a863-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="5a863-112">如何：通过修改 DBML 文件生成自定义代码</span><span class="sxs-lookup"><span data-stu-id="5a863-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="5a863-113">描述如何从 DBML 元数据文件生成 Visual Basic 或 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="5a863-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="5a863-114">如何：验证 DBML 和外部映射文件</span><span class="sxs-lookup"><span data-stu-id="5a863-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="5a863-115">介绍如何验证您已修改的映射文件（高级）。</span><span class="sxs-lookup"><span data-stu-id="5a863-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="5a863-116">如何：使实体可序列化</span><span class="sxs-lookup"><span data-stu-id="5a863-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="5a863-117">介绍如何添加适当的属性以使实体可序列化。</span><span class="sxs-lookup"><span data-stu-id="5a863-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="5a863-118">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="5a863-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="5a863-119">介绍如何使用代码编辑器编写您自己的映射代码，或自定义已自动生成的代码。</span><span class="sxs-lookup"><span data-stu-id="5a863-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5a863-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="5a863-120">Related Sections</span></span>  
 [<span data-ttu-id="5a863-121">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="5a863-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="5a863-122">提供有关 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对象模型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a863-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="5a863-123">使用 LINQ to SQL 的典型步骤</span><span class="sxs-lookup"><span data-stu-id="5a863-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="5a863-124">说明在实现 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序时应遵循的典型步骤。</span><span class="sxs-lookup"><span data-stu-id="5a863-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
