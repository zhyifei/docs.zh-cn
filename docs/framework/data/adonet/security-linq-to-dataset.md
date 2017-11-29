---
title: "安全性 (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c0c919bb5be12005850b81059fc641f6f25b06bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="security-linq-to-dataset"></a><span data-ttu-id="abddc-102">安全性 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="abddc-102">Security (LINQ to DataSet)</span></span>
<span data-ttu-id="abddc-103">本主题讨论 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 中的安全性问题。</span><span class="sxs-lookup"><span data-stu-id="abddc-103">This topic discusses security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="passing-a-query-to-an-untrusted-component"></a><span data-ttu-id="abddc-104">将查询传递到不受信任的组件</span><span class="sxs-lookup"><span data-stu-id="abddc-104">Passing a Query to an Untrusted Component</span></span>  
 <span data-ttu-id="abddc-105">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询可在程序中的一点表述，而在另一点执行。</span><span class="sxs-lookup"><span data-stu-id="abddc-105">A [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query can be formulated in one point of a program and executed in a different one.</span></span> <span data-ttu-id="abddc-106">在表述查询的点，查询可引用任何可见元素在该点，例如调用方法所属的类或者表示局部变量/自变量的符号的私有成员。</span><span class="sxs-lookup"><span data-stu-id="abddc-106">At the point where the query is formulated, the query can reference any element that is visible at that point, such as private members of the class that the calling method belongs to, or symbols representing local variables/arguments.</span></span> <span data-ttu-id="abddc-107">在执行时，查询能有效访问那些查询在表述中引用的成员，即使其中调用代码没有可见性。</span><span class="sxs-lookup"><span data-stu-id="abddc-107">At execution time, the query will effectively be able to access those members that were referenced by the query at formulation, even if the calling code does not have visibility into them.</span></span> <span data-ttu-id="abddc-108">执行查询的代码没有任意添加的可见性，因为它无法选择访问内容。</span><span class="sxs-lookup"><span data-stu-id="abddc-108">The code that executes the query does not have arbitrary added visibility, in that it cannot choose what to access.</span></span> <span data-ttu-id="abddc-109">它能严格访问查询所访问的内容，并且仅通过查询本身访问。</span><span class="sxs-lookup"><span data-stu-id="abddc-109">It will be able to access strictly what the query accesses, and only through the query itself.</span></span>  
  
 <span data-ttu-id="abddc-110">这意味着将查询的引用传递到其他代码段即表示信任接收该查询的组件，组件可访问查询引用的所有公共成员和私有成员。</span><span class="sxs-lookup"><span data-stu-id="abddc-110">This implies that by passing a reference to a query to another piece of code the component receiving the query is being trusted with access to all public and private members that the query refers to.</span></span> <span data-ttu-id="abddc-111">通常情况下，不应将 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询传递到不受信任的组件，除非查询已经过仔细构造，使它不能公开应保留为私有的信息。</span><span class="sxs-lookup"><span data-stu-id="abddc-111">In general, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries should not be passed to untrusted components, unless the query has been carefully constructed so that it does not expose information that should be kept private.</span></span>  
  
## <a name="external-input"></a><span data-ttu-id="abddc-112">外部输入</span><span class="sxs-lookup"><span data-stu-id="abddc-112">External Input</span></span>  
 <span data-ttu-id="abddc-113">应用程序常常采用外部输入（来自用户或其他外部代理），并根据该输入执行操作。</span><span class="sxs-lookup"><span data-stu-id="abddc-113">Applications often take external input (from a user or another external agent) and perform actions based on that input.</span></span>  <span data-ttu-id="abddc-114">情况下[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]，应用程序可能会构造以某种方式，基于外部输入或输入在查询中使用外部查询。</span><span class="sxs-lookup"><span data-stu-id="abddc-114">In the case of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], the application might construct a query in a certain way, based on external input or use external input in the query.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="abddc-115"> 查询可在任何接受文本的位置接受参数。</span><span class="sxs-lookup"><span data-stu-id="abddc-115"> queries accept parameters everywhere that literals are accepted.</span></span> <span data-ttu-id="abddc-116">应用程序开发人员应使用参数化查询，而不是将来自外部代理的文本直接注入查询。</span><span class="sxs-lookup"><span data-stu-id="abddc-116">Application developers should use parameterized queries, rather than injecting literals from an external agent directly into the query.</span></span>  
  
 <span data-ttu-id="abddc-117">任何直接或间接从用户或外部代理派生的输入都可能包含利用目标语言的语法来执行未授权操作的内容。</span><span class="sxs-lookup"><span data-stu-id="abddc-117">Any input directly or indirectly derived from the user or an external agent might have content that leverages the syntax of the target language in order to perform unauthorized actions.</span></span> <span data-ttu-id="abddc-118">这称为 SQL 注入式攻击，是以目标语言为 Transact-SQL 的攻击模式命名的。</span><span class="sxs-lookup"><span data-stu-id="abddc-118">This is known as a SQL injection attack, named after an attack pattern where the target language is Transact-SQL.</span></span> <span data-ttu-id="abddc-119">恶意用户利用这种直接注入到查询的用户输入删除数据库表、产生拒绝服务或者更改所执行操作的性质。</span><span class="sxs-lookup"><span data-stu-id="abddc-119">User input injected directly into the query is used to drop a database table, cause a denial of service, or otherwise change the nature of the operation being performed.</span></span> <span data-ttu-id="abddc-120">尽管在 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]中可以撰写查询，但是要通过对象模型 API 执行。</span><span class="sxs-lookup"><span data-stu-id="abddc-120">Although query composition is possible in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], it is performed through the object model API.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="abddc-121">通过使用字符串操作或串联，因为它们都是在 TRANSACT-SQL，并不容易受到 SQL 注入式攻击在传统意义上不编写查询。</span><span class="sxs-lookup"><span data-stu-id="abddc-121"> queries are not composed by using string manipulation or concatenation, as they are in Transact-SQL, and are not susceptible to SQL injection attacks in the traditional sense.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abddc-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abddc-122">See Also</span></span>  
 [<span data-ttu-id="abddc-123">编程指南</span><span class="sxs-lookup"><span data-stu-id="abddc-123">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
