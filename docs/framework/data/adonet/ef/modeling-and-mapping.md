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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 82bb3ca8bd5ef0659bbb222753b3225288fcbcfc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="modeling-and-mapping"></a>建模和映射
在[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]中，可以采用最适合您应用程序的方式定义概念模型、存储模型以及这两种模型之间的映射。 中的实体数据模型工具[!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]允许你创建。[edmx 文件](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)从数据库或图形模型，然后更新该文件时的数据库或模型发生更改。  
  
 实体框架 4.1 开始，还可使用 Code First 开发以编程方式创建模型。 对于 Code First 开发，有两种不同的方案。 在两种情况下，开发人员通过对 .NET Framework 类定义进行编码来定义模型，然后可选择使用数据注释或 fluent API 指定其他映射或配置。  
  
 有关详细信息，请参阅[创建和映射概念模型](http://go.microsoft.com/fwlink/?LinkId=235016)。  
  
 你还可以使用 EDM 生成器，这是附带[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]。 EdmGen.exe 从现有数据源生成 .csdl、 .ssdl 和 .msl 文件。 也可以手动创建模型和映射内容。 有关详细信息，请参阅[EDM 生成器 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)。
