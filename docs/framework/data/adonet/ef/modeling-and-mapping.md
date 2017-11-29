---
title: "建模和映射"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2004b950f1096f574734259ba02944577dd9adc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="02f0b-102">建模和映射</span><span class="sxs-lookup"><span data-stu-id="02f0b-102">Modeling and Mapping</span></span>
<span data-ttu-id="02f0b-103">在[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]中，可以采用最适合您应用程序的方式定义概念模型、存储模型以及这两种模型之间的映射。</span><span class="sxs-lookup"><span data-stu-id="02f0b-103">In the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="02f0b-104">中的实体数据模型工具[!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]允许你创建。[edmx 文件](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)从数据库或图形模型，然后更新该文件时的数据库或模型发生更改。</span><span class="sxs-lookup"><span data-stu-id="02f0b-104">The Entity Data Model Tools in [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] allow you to create an .[edmx file](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="02f0b-105">实体框架 4.1 开始，还可使用 Code First 开发以编程方式创建模型。</span><span class="sxs-lookup"><span data-stu-id="02f0b-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="02f0b-106">对于 Code First 开发，有两种不同的方案。</span><span class="sxs-lookup"><span data-stu-id="02f0b-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="02f0b-107">在两种情况下，开发人员通过对 .NET Framework 类定义进行编码来定义模型，然后可选择使用数据注释或 fluent API 指定其他映射或配置。</span><span class="sxs-lookup"><span data-stu-id="02f0b-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="02f0b-108">有关详细信息，请参阅[创建和映射概念模型](http://go.microsoft.com/fwlink/?LinkId=235016)。</span><span class="sxs-lookup"><span data-stu-id="02f0b-108">For more information, see [Creating and Mapping a Conceptual Model](http://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="02f0b-109">你还可以使用 EDM 生成器，这是附带[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="02f0b-109">You can also use the EDM Generator, which is included with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="02f0b-110">EdmGen.exe 从现有数据源生成 .csdl、 .ssdl 和 .msl 文件。</span><span class="sxs-lookup"><span data-stu-id="02f0b-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="02f0b-111">也可以手动创建模型和映射内容。</span><span class="sxs-lookup"><span data-stu-id="02f0b-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="02f0b-112">有关详细信息，请参阅[EDM 生成器 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="02f0b-112">For more information, see [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span></span>
