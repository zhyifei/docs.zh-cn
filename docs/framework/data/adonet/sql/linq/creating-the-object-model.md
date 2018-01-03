---
title: "创建对象模型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 37f96338868183e8bf0397d9c0d09719fa3f7049
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-object-model"></a><span data-ttu-id="ddb33-102">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="ddb33-102">Creating the Object Model</span></span>
<span data-ttu-id="ddb33-103">您可以从现有数据库中创建对象模型并以该模型的默认状态使用它。</span><span class="sxs-lookup"><span data-stu-id="ddb33-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="ddb33-104">您还可以自定义该模型的许多方面及其行为。</span><span class="sxs-lookup"><span data-stu-id="ddb33-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="ddb33-105">如果你使用[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]，你可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来创建对象模型。</span><span class="sxs-lookup"><span data-stu-id="ddb33-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddb33-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="ddb33-106">In This Section</span></span>  
 [<span data-ttu-id="ddb33-107">如何：在 Visual Basic 或 C# 中生成对象模型</span><span class="sxs-lookup"><span data-stu-id="ddb33-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="ddb33-108">介绍如何使用 SQLMetal 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="ddb33-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="ddb33-109">还为 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 用户提供了指向[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]的链接。</span><span class="sxs-lookup"><span data-stu-id="ddb33-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] users</span></span>  
  
 [<span data-ttu-id="ddb33-110">如何：将对象模型作为外部文件生成</span><span class="sxs-lookup"><span data-stu-id="ddb33-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="ddb33-111">介绍如何生成外部映射文件，而不是使用基于属性的映射。</span><span class="sxs-lookup"><span data-stu-id="ddb33-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="ddb33-112">如何：通过修改 DBML 文件生成自定义代码</span><span class="sxs-lookup"><span data-stu-id="ddb33-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="ddb33-113">介绍如何从 DBML 元数据文件生成 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 或 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="ddb33-113">Describes how to generate [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="ddb33-114">如何：验证 DBML 和外部映射文件</span><span class="sxs-lookup"><span data-stu-id="ddb33-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="ddb33-115">介绍如何验证您已修改的映射文件（高级）。</span><span class="sxs-lookup"><span data-stu-id="ddb33-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="ddb33-116">如何：使实体可序列化</span><span class="sxs-lookup"><span data-stu-id="ddb33-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="ddb33-117">介绍如何添加适当的属性以使实体可序列化。</span><span class="sxs-lookup"><span data-stu-id="ddb33-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="ddb33-118">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="ddb33-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="ddb33-119">介绍如何使用代码编辑器编写您自己的映射代码，或自定义已自动生成的代码。</span><span class="sxs-lookup"><span data-stu-id="ddb33-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ddb33-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="ddb33-120">Related Sections</span></span>  
 [<span data-ttu-id="ddb33-121">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="ddb33-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="ddb33-122">提供有关 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对象模型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ddb33-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="ddb33-123">使用 LINQ to SQL 的典型步骤</span><span class="sxs-lookup"><span data-stu-id="ddb33-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="ddb33-124">说明在实现 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序时应遵循的典型步骤。</span><span class="sxs-lookup"><span data-stu-id="ddb33-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
