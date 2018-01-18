---
title: "部署注意事项（实体框架）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a847a22-4eb8-4565-b18b-453bbca070db
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 490a0e4395e27aee15ca2d649e114a4c8b7eeeb9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="deployment-considerations-entity-framework"></a>部署注意事项（实体框架）
本主题提供有关部署使用 ADO.NET 实体框架进行数据访问的应用程序的信息。 有关实体框架的详细信息，请参阅[入门](../../../../../docs/framework/data/adonet/ef/getting-started.md)。  
  
 实体框架提供了一组与 Visual Studio 集成的工具，使得在 Visual Studio 中进行开发更加容易。 有关详细信息，请参阅[ADO.NET 实体数据模型工具](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)。 本主题未介绍如何使用特定技术部署基于实体框架的应用程序。  
  
 Visual Studio 提供用于分发和部署应用程序的工具（例如 ClickOnce 部署）。 有关详细信息，请参阅[部署应用程序和组件](/visualstudio/deployment/deploying-applications-services-and-components)Visual Studio 文档中。  
  
 部署使用实体框架的应用程序时需要考虑以下注意事项：  
  
-   自 .NET Framework 3.5 Service Pack 1 (SP1) 起实体框架成为 .NET Framework 的一个组件。 部署基于 Entity Framework 的应用程序时必须确保安装了 .NET Framework 3.5 SP1 或更高版本。  
  
-   当概念模型由实体数据模型向导生成时，将在应用程序配置文件中创建连接字符串。 模型和映射文件可以作为应用程序资源嵌入，或复制到输出目录中。 默认情况下，它们部署为嵌入的应用程序资源。 使用实体设计器文件的 `Metadata Artifact Processing` 属性可选择这些选项之一。 有关详细信息，请参阅[如何： 复制模型和映射文件添加到输出目录](http://msdn.microsoft.com/en-us/e2c9820f-1705-457e-9fdb-8b289f3179b4)。  
  
-   确保模型和映射信息（以概念架构定义语言 (CSDL)、存储架构定义语言 (SSDL) 和映射规范语言 (MSL) 表示）与应用程序一起部署在由连接字符串指定的位置。 有关详细信息，请参阅[连接字符串](../../../../../docs/framework/data/adonet/ef/connection-strings.md)。  
  
-   在将模型和映射信息作为应用程序资源嵌入时，每次更新概念模型时，都必须重新编译和重新部署应用程序。  
  
-   因为实体框架是 .NET Framework 的一个组件，因此在 .NET Framework 许可协议许可的情况下可以与您的应用程序一起重新分发该组件。  
  
## <a name="see-also"></a>请参阅  
 [ADO.NET 实体框架](../../../../../docs/framework/data/adonet/ef/index.md)  
 [开发和部署注意事项](../../../../../docs/framework/data/adonet/ef/development-and-deployment-considerations.md)
