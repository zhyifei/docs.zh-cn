---
title: 建模和映射
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 847d518710b21df714343b541401ff7fc8443fb3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034016"
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="db201-102">建模和映射</span><span class="sxs-lookup"><span data-stu-id="db201-102">Modeling and Mapping</span></span>
<span data-ttu-id="db201-103">在[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]中，可以采用最适合您应用程序的方式定义概念模型、存储模型以及这两种模型之间的映射。</span><span class="sxs-lookup"><span data-stu-id="db201-103">In the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="db201-104">Visual Studio 中的实体数据模型工具允许您创建。[edmx 文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))从数据库或图形模型，然后更新该文件的数据库或模型发生更改时。</span><span class="sxs-lookup"><span data-stu-id="db201-104">The Entity Data Model Tools in Visual Studio allow you to create an .[edmx file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="db201-105">实体框架4.1 开始，还可使用 Code First 开发以编程方式创建模型。</span><span class="sxs-lookup"><span data-stu-id="db201-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="db201-106">对于 Code First 开发，有两种不同的方案。</span><span class="sxs-lookup"><span data-stu-id="db201-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="db201-107">在两种情况下，开发人员通过对 .NET Framework 类定义进行编码来定义模型，然后可选择使用数据注释或 fluent API 指定其他映射或配置。</span><span class="sxs-lookup"><span data-stu-id="db201-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="db201-108">有关详细信息，请参阅[创建和映射概念模型](https://go.microsoft.com/fwlink/?LinkId=235016)。</span><span class="sxs-lookup"><span data-stu-id="db201-108">For more information, see [Creating and Mapping a Conceptual Model](https://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="db201-109">此外可以使用 EDM 生成器，它附带[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="db201-109">You can also use the EDM Generator, which is included with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="db201-110">EdmGen.exe 从现有数据源生成 .csdl、 .ssdl 和 .msl 文件。</span><span class="sxs-lookup"><span data-stu-id="db201-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="db201-111">也可以手动创建模型和映射内容。</span><span class="sxs-lookup"><span data-stu-id="db201-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="db201-112">有关详细信息，请参阅[EDM 生成器 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="db201-112">For more information, see [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span></span>
