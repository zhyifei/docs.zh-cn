---
title: 建模和映射
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 33064d35b7ac4c469df3ca6f0111cc84ef10eb08
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248490"
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="94da2-102">建模和映射</span><span class="sxs-lookup"><span data-stu-id="94da2-102">Modeling and Mapping</span></span>
<span data-ttu-id="94da2-103">在[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]中，可以采用最适合您应用程序的方式定义概念模型、存储模型以及这两种模型之间的映射。</span><span class="sxs-lookup"><span data-stu-id="94da2-103">In the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="94da2-104">使用 Visual Studio 中的实体数据模型工具可创建。数据库或图形模型中的[edmx 文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))，然后在数据库或模型发生更改时更新该文件。</span><span class="sxs-lookup"><span data-stu-id="94da2-104">The Entity Data Model Tools in Visual Studio allow you to create an .[edmx file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="94da2-105">实体框架4.1 开始，还可使用 Code First 开发以编程方式创建模型。</span><span class="sxs-lookup"><span data-stu-id="94da2-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="94da2-106">对于 Code First 开发，有两种不同的方案。</span><span class="sxs-lookup"><span data-stu-id="94da2-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="94da2-107">在两种情况下，开发人员通过对 .NET Framework 类定义进行编码来定义模型，然后可选择使用数据注释或 fluent API 指定其他映射或配置。</span><span class="sxs-lookup"><span data-stu-id="94da2-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="94da2-108">有关详细信息，请参阅[创建和映射概念模型](https://go.microsoft.com/fwlink/?LinkId=235016)。</span><span class="sxs-lookup"><span data-stu-id="94da2-108">For more information, see [Creating and Mapping a Conceptual Model](https://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="94da2-109">你还可以使用 .NET Framework 附带的 EDM 生成器。</span><span class="sxs-lookup"><span data-stu-id="94da2-109">You can also use the EDM Generator, which is included with the .NET Framework.</span></span> <span data-ttu-id="94da2-110">EdmGen.exe 从现有数据源生成 .csdl、 .ssdl 和 .msl 文件。</span><span class="sxs-lookup"><span data-stu-id="94da2-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="94da2-111">也可以手动创建模型和映射内容。</span><span class="sxs-lookup"><span data-stu-id="94da2-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="94da2-112">有关详细信息，请参阅[EDM 生成器（edmgen.exe）](edm-generator-edmgen-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="94da2-112">For more information, see [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md).</span></span>
